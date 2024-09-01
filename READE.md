* 测试acistol中gme_is_equal函数，容差为SPAresabs，输入参数为两个单位向量，包括以下几种情况：
 * case 1：输入的两非零向量之差处于容差值位置
 * case 2：输入的两非零向量之差大于容差值位置
 * case 3：输入的两非零向量之差小于容差值位置
 * case 4：输入两非零向量相等
 * case 5：输入两非零向量不平行
 * 待测试情况：
 */
/*
 * @brief 判断两个单位向量在SPAresabs范围内是否相等（输入的两非零向量之差处于容差值位置）
 */
TEST_F(AcistolTest, IsEqualunit1) {
    SPAunit_vector v1(1, 0, 0);
    SPAunit_vector v2(1, 0, 0.000001);
    logical test_res = gme_is_equal(v1, v2);
    logical gt_res = is_equal(v1, v2);
    EXPECT_TRUE(test_res == gt_res);
}
/*
 * @brief 判断两个单位向量在SPAresabs范围内是否相等（输入的两非零向量之差大于容差值位置）
 */
TEST_F(AcistolTest, IsEqualunit2) {
    SPAunit_vector v1(1, 0, 0);
    SPAunit_vector v2(1, 0, 0.0001);
    logical test_res = gme_is_equal(v1, v2);
    logical gt_res = is_equal(v1, v2);
    EXPECT_TRUE(test_res == gt_res);
}
/*
 * @brief 判断两个单位向量在SPAresabs范围内是否相等（输入的两非零向量之差小于容差值位置）
 */
TEST_F(AcistolTest, IsEqualunit3) {
    SPAunit_vector v1(1, 0, 0);
    SPAunit_vector v2(1, 0, 0.00000005);
    logical test_res = gme_is_equal(v1, v2);
    logical gt_res = is_equal(v1, v2);
    EXPECT_TRUE(test_res == gt_res);
}
/*
 * @brief 判断两个单位向量在SPAresabs范围内是否相等（输入两非零向量相等）
 */
TEST_F(AcistolTest, IsEqualunit4) {
    SPAunit_vector v1(1, 0, 0);
    SPAunit_vector v2(1, 0, 0);
    logical test_res = gme_is_equal(v1, v2);
    logical gt_res = is_equal(v1, v2);
    EXPECT_TRUE(test_res == gt_res);
}
/*
 * @brief 判断两个单位向量在SPAresabs范围内是否相等（输入两非零向量不平行）
 */
TEST_F(AcistolTest, IsEqualunit5) {
    SPAunit_vector v1(sqrt(1.0 / 3), sqrt(1.0 / 3), sqrt(1.0 / 3));
    SPAunit_vector v2(1, 0, 0);
    logical test_res = gme_is_equal(v1, v2);
    logical gt_res = is_equal(v1, v2);
    EXPECT_TRUE(test_res == gt_res);
}
