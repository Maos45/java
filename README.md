＃Java先定义一个字符串添加古诗词，然后实例化该古诗。
			String text = "汉皇重色思倾国御宇多年求不得杨家有女初长成养在深闺人未识天生丽质难自弃一朝选在君王侧回眸一笑百媚生六宫粉黛无颜色春寒赐浴华清池温泉水滑洗凝脂侍儿扶起娇无力始是新承恩泽时云鬓花颜金步摇芙蓉帐暖度春宵春宵苦短日高起从此君王不早朝";
			StringBuffer s = new StringBuffer(text);
  之后遍历该古诗并进行整理打印。
      for (int i = 7; i < s.length(); i = i + 15) {
				s.insert(i, ",");
			}
			for (int i = 15; i < s.length() + 1; i = i + 16) {
				s.insert(i, "。");
			}
			for (int i = 16; i < s.length(); i = i + 17) {
				s.insert(i, "\n");
			}
			System.out.println(s);
  最后添加查询字数出现的方法。
       Scanner in = new Scanner(System.in);// 定义scanner
			System.out.println("请输入要统计出现次数的文字:");//输入文字
			String word = in.nextLine();
			String a = s.toString();
			int indexStart = 0;
			int count = 0;
			while (true) {
				int times = a.indexOf(word, indexStart);
				if (times >= 0) {
					count++;
					indexStart = times + word.length();
				} else {
					break;
				}
			}
			if (count == 0) {
				System.out.println("该字没有出现。");
			} else {
				System.out.println("该文字出现了" + count + "次。");
			}
		} 
	}
  中间用try{...}catch{...}进行异常处理。
  	try {...}
    catch (Exception e) {
			System.err.println("出现异常！" + e.toString());
		}
