#RecyclerView的可以响应点击事件的Adapter
##1.使用ClickableRcvAdapter作为你适配器的父类，在onBindViewHolder方法中调用bindListener(holder);

##2.在外部对你的Adapter进行点击事件的监听注册

例如：
   第一步:
 	@Override
        public void onBindViewHolder(MyHolder holder, int position) {
            bindListener(holder);
        }
   第二步:
	rcvAdapter.setOnItemClickLitener(new ClickableRcvAdapter.OnItemClickLitener() {
            @Override
            public void onItemClick(View view, int position) {
                ToastUtils.showToast("click " + position);
            }

            @Override
            public boolean onItemLongClick(View view, int position) {
                return false;
            }
        });
