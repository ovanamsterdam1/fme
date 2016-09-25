#import "GGView.h"
#import "GGDraggableView.h"

@interface GGView ()
@property (nonatomic, strong) GGDraggableView *draggableView;
@end

@implementation GGView

- (id)init
{
    self = [super init];
    if (!self) return nil;

    self.backgroundColor = [UIColor whiteColor];
    [self loadDraggableCustomView];

    return self;
}

- (void)loadDraggableCustomView
{
    self.draggableView = [[GGDraggableView alloc] init];
    [self addSubview:self.draggableView];
}

- (void)layoutSubviews {
    [super layoutSubviews];
    self.draggableView.frame = CGRectMake(60, 60, 200, 260);
}

@end
