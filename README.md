### ��Ҫ����
####����һ�׿����Ļ������ ��װ��һЩ�������ù�����ķ�װ
���������Դ�������ϵ�һЩ������Լ������ �����Ǻܻ�������ʵ�õĶ���
�ʺϳ�ѧ�ߵ���Ŀ��ܴʹ��

1.Activity��Fragment֮���һ����뻥��ת��
2.AppManager��Activity���ص���ջ�еĹ��� ��ֹ�ڴ����
3.ActivityUtil��Activity��ת�ķ�װ �Լ�Ԥ����ת����
4.Fragment����onActivityResult���ص�����
5.SharedPreferences�ķ�װ�Լ��������ݵ�AES����
6.Log��ӡ�ķ�װ

�ڿ��������п��ܻ���������ģ��ĵ�����Activity��Ҫת��ΪFragment������Fragment��Ҫת��ΪActivity�� �����ʱ�����ǿ���Ҫ�Ķ������Ĵ�������ɣ� ���������һ��ʼ�Ͷ����Activity��Fragment����Ҫ�÷�����һ�µģ� ���ʱ�����Ǿ�ֻ��Ҫ�滻�Ҽ̳еĸ�������ˡ� ���ʱ�����Ҫ����һ���õ�BaseActivity��BaseFragment��
###һ��Activity��Fragment֮���һ����뻥��ת��
#### Fragment����
    public class TestFragment extends BaseFragment implements View.OnClickListener{
        Button TestOne, TestTwo;
    
        @Override
        public void onInit(Bundle savedInstanceState) {
            setContentView(R.layout.activity_test);
            initUI();
            initEvent();
        }
    
        private void initUI() {
            TestOne = getId(R.id.TestOne);
            TestTwo = getId(R.id.TestTwo);
        }
    
        private void initEvent() {
            TestOne.setOnClickListener(this);
            TestTwo.setOnClickListener(this);
        }
    
        @Override
        public void onClick(View v) {
            switch (v.getId()) {
                case R.id.TestOne:
                    ActivityUtil.next(getActivity(), AlbumActivity.class);
                    break;
                case R.id.TestTwo:
                    ActivityUtil.next(getActivity(), AlbumActivity.class);
                    break;
                default:
                    break;
            }
        }
    }
#### Activity����
    public class TestActivity extends BaseActivity implements View.OnClickListener {
        Button TestOne, TestTwo;
    
        @Override
        public void onInit(Bundle savedInstanceState) {
            setContentView(R.layout.activity_test);
            initUI();
            initEvent();
        }
    
        private void initUI() {
            TestOne = getId(R.id.TestOne);
            TestTwo = getId(R.id.TestTwo);
        }
    
        private void initEvent() {
            TestOne.setOnClickListener(this);
            TestTwo.setOnClickListener(this);
        }
    
        @Override
        public void onClick(View v) {
            switch (v.getId()) {
                case R.id.TestOne:
                    ActivityUtil.next(getActivity(), AlbumActivity.class);
                    break;
                case R.id.TestTwo:
                    ActivityUtil.next(getActivity(), AlbumActivity.class);
                    break;
                default:
                    break;
            }
        }
    }
###����
��������Ĵ�����Կ��� ����ֻ��Ҫͨ���ı�̳и���Ϳ���ʵ��Activity��Fragment��ת�� ��
������Fragment����ʵ����Activity��setContentView����

onCreate(Bundle savedInstanceState)�滻ΪonInit(Bundle savedInstanceState)

findViewById��int id���滻ΪgetId��int id�����Ҳ���Ҫ���͵�ת��


###����AppManager��Activity���ص���ջ�еĹ���
����಻�ض�˵�� ��
����Activity��ʱ��activityѹ���ջ ������ʱ�򵯳���ջɾ����ջ���ݡ�
��������ѿ�����Activity
����һЩ�Ż� ��ֹ�ڴ����

###����ActivityUtil��Activity��ת�ķ�װ �Լ�Ԥ����ת����
    			//��ͨ��ת
                ActivityUtil.next(getActivity(), AlbumActivity.class);
                //��������ת
                Bundle extras = new Bundle();
                extras.putString("key","��������");
                ActivityUtil.next(getActivity(), AlbumActivity.class,extras);
                //������ֵ��ת
                ActivityUtil.next(getActivity(), AlbumActivity.class,extras,100);
                //��ת��������ǰActivity
                ActivityUtil.next(getActivity(), AlbumActivity.class,true);
                //��ת���޸�Ĭ���л�����
                ActivityUtil.next(getActivity(), AlbumActivity.class,R.anim.in_from_right,
                        R.anim.out_to_left);
                //����
                ActivityUtil.goBack(getActivity());
                //���η���
                ActivityUtil.goBackWithResult(getActivity(),100,extras); 
				.......


���Զ���ת����ͳһ�淶�Ĺ���

�������ҾͲ�һһ��˵��  ����һ��Դ�� �Լ���ĥһ�°�   
��ӭ���� ��ӭ���� ��ӭ�²�
