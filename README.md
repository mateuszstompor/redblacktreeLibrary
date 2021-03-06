# Red Black Tree
###### Tests status
[![Build Status](https://www.travis-ci.org/mateuszstompor/RedBlackTree.svg?branch=master)](https://www.travis-ci.org/mateuszstompor/RedBlackTree)
<p align="center">
  <img src="https://image.ibb.co/n0LNG5/rbt.png">
</p>

## Features
<ul>
    <li>Objective-C 2.0 (with ARC)</li>
    <li>Unit-Tests</li>
    <li>Coverage 80+</li>
</ul>

## About
macOS framework made in a way similar to all foundation containers. It is a generic data structure, has interface similar to all other foundation containers and is tested.
It is meant to be used as a base for other, higher level data structure, for example a dictionary. It is key only tree. In oreder to use it as a container you shoud
override the main class, create a specialized type which contains both key and value and be able to return a value for given key.

### Properties of Red-Black Tree
<ul>
    <li>Each node is either red or black</li>
    <li>The root is black</li>
    <li>All leaves and nil-children are considered to be black.</li>
    <li>If a node is red, then both its children are black</li>
    <li>Every path from a given node to any of its descendant nil nodes contains the same number of black nodes</li>
</ul>

## Interface
```objective-c
@interface RedBlackTree<T> : NSObject

@property (nonatomic, readonly) NSUInteger count;

- (instancetype)          init;
- (void)                  addObject: (T) object;
- (BOOL)                  containsObject: (T) anObject;
- (void)                  removeObject: (T) anObject;
- (T _Nullable)           objectForKey: (T _Nonnull) anObject;

@end
```


## Example usage

```objective-c

#import <RedBlackTree/RedBlackTree.h>

int main(int argc, const char * argv[]) {
    @autoreleasepool {
        // initialize
        RedBlackTree<NSNumber*>* tree;
        tree = [[RedBlackTree alloc] init];

        // add an element
        [tree addObject: [NSNumber numberWithInt:3]];

        // count elements
        [tree count];

        // remove an element
        [tree removeObject: [NSNumber numberWithInt:3]];

        // check if it contains an object
        [tree containsObject: [NSNumber numberWithInt:3]];
        
        // returns given key from the tree
        [tree objectForKey: [NSNumber numberWithInt:3]];
    }
    return 0;
}

```
