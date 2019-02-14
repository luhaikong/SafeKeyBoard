# SafeKeyBoard
安卓自定义软键盘，支持安卓4.4及以上

使用方法：

1、在需要使用安全软键盘的activity中声明：

   private SafeKeyboard safeKeyboard;
   
2、在xml布局文件底部新增“控件容器”[keyboardViewPlace]：

![cmd-markdown-logo](https://github.com/luhaikong/SafeKeyBoard/blob/master/picture/xml%E6%A0%B7%E5%BC%8F.png)
        
3、绑定需要使用安全软键盘的控件：

  mPasswordView = (EditText) findViewById(R.id.password);
  
  // 自定义软键盘使用开始
  
  LinearLayout keyboardContainer = (LinearLayout) findViewById(R.id.keyboardViewPlace);  
  View view = LayoutInflater.from(this).inflate(R.layout.layout_keyboard_containor, null);  
  safeKeyboard = new SafeKeyboard(getApplicationContext(), keyboardContainer, mPasswordView,  
            R.layout.layout_keyboard_containor, view.findViewById(R.id.safeKeyboardLetter).getId());  
  safeKeyboard.setDelDrawable(this.getResources().getDrawable(R.drawable.icon_del));  
  safeKeyboard.setLowDrawable(this.getResources().getDrawable(R.drawable.icon_capital_default));  
  safeKeyboard.setUpDrawable(this.getResources().getDrawable(R.drawable.icon_capital_selected));  

  // 自定义软键盘使用结束
