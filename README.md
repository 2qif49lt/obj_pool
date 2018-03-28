# obj_pool
A lock-free object pool!

obj_pool对象池内部是由固定大小的指针数组实现的环形队列，允许多线程访问。

#### 特点
- 单文件
- lock-free
- cache命中友好
- 高性能
- 可轻易实现批量操作。
- 基于c++11/14，接口使用方便。
- 经过多重维度测试可靠。

#### 示例
```
xhb::obj_pool<xhbtest::objtest> pool;

xhbtest::objtest* a = pool.get_raw();
pool.put_raw(a);

{
    auto b = pool.get(); // unique_ptr
    auto c = pool.get("change");
}
```
