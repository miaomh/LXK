#include <gtest/gtest.h>

// 被测试的功能
int add(int a, int b) {
    return a + b;
}

// 测试用例
TEST(AdditionTest, HandlesPositiveNumbers) {
    EXPECT_EQ(add(2, 3), 5);       // 期望 2 + 3 等于 5
    EXPECT_EQ(add(10, 20), 30);    // 期望 10 + 20 等于 30
}

TEST(AdditionTest, HandlesNegativeNumbers) {
    EXPECT_EQ(add(-1, -1), -2);    // 期望 -1 + (-1) 等于 -2
    EXPECT_EQ(add(-5, 3), -2);     // 期望 -5 + 3 等于 -2
}

// 主函数，运行所有测试用例
int main(int argc, char **argv) {
    ::testing::InitGoogleTest(&argc, argv);
    return RUN_ALL_TESTS();
}

