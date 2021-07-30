# 加载刷新组件无数据

```java
private void initList() {
    mRefreshView.setEmptyLayoutId(R.layout.view_no_data_video_long_details);
    // 去掉这行将会数据注入不成功
    mRefreshView.setLayoutManager(new LinearLayoutManager(mContext));
    mRefreshView.setDataHelper(new CommonRefreshView.DataHelper<VideoWithAds>() {
        @Override
        public RefreshAdapter<VideoWithAds> getAdapter() {
            return ...;
        }

        @Override
        public void loadData(int p, HttpCallback callback) {
					...
        }

        @Override
        public List<VideoWithAds> processData(String[] info) {
            return ...;
        }

        @Override
        public void onRefreshSuccess(List<VideoWithAds> list, int listCount) {
            ...
        }

        @Override
        public void onRefreshFailure() {

        }

        @Override
        public void onLoadMoreSuccess(List<VideoWithAds> loadItemList, int loadItemCount) {
          ...
        }

        @Override
        public void onLoadMoreFailure() {

        }
        });
}
```

一定要加`mRefreshView.setLayoutManager(new LinearLayoutManager(mContext));`，否则就算请求到数据也无法赋值及显示，具体看项目内代码；