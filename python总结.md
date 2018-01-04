+ 注意区分位置参数和关键字参数
def send_keys(self, keyserver, *keyids):
send_keys(keyserver=xxx, 'hello')这样的调用是无法通过的
