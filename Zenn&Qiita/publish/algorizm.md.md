rubyのアルゴリズムを使ったコードの書き方で学んだことを書いておきます。
二分探索で年齢を当てるアルゴリズムを作ってみた
```
```
```
age_min = 20

age_max = 35

found = false

  

puts "20歳以上36歳未満の年齢を思い浮かべてください。"

puts "私の質問に「高い」「低い」「正解」で答えてください。"

  

while age_min <= age_max

  

guess = (age_min + age_max) / 2

puts "あなたの年齢は#{guess}歳ですか？"

response = gets.chomp

  

case response

when "高い"

puts "高いです。"

age_min = guess + 1

when "低い"

puts "低いです。"

age_max = guess - 1

when "正解"

puts "正解です。"

found = true

break

else

puts "高い低い正解のみで答える。"

end

end

  

if found

puts "ゲームが終了しました！"

puts "あなたの年齢は#{guess}歳ですね！"

exit

else

puts "その年齢は範囲内にないようです。"

exit

end

```
```
```
わからなかったこと
* caseの処理問題
	* exitのコードの意味
	  プログラム自体を修了するメソッド。
	  caseのところに書いていたがこれだと成功した後に何か実行しようとしてもできない
	* breakのコードの意味
	  breakはループ処理を終了させるために定義する
	* break ifについて
```
	  if 条件
	  break
	  end
```
　　　　これと同じ動きをする
　　　　つまり特定の条件になったらループ処理を終了するということ
* getsの処理について
  rubyではどこにgetsを書いてもそこの時点で入力画面にすることができる。この下のコード例だと正解と入力した後にメッセージを入力できるようになっている。
```
age_min = 20

age_max = 35

found = false

  

puts "20歳以上36歳未満の年齢を思い浮かべてください。"

puts "私の質問に「高い」「低い」「正解」で答えてください。"

  

while age_min <= age_max

  

guess = (age_min + age_max) / 2

puts "あなたの年齢は#{guess}歳ですか？"

response = gets.chomp

  

case response

when "高い"

puts "高いです。"

age_min = guess + 1

when "低い"

puts "低いです。"

age_max = guess - 1

when "正解"

puts "正解です。"

found = true

break if found === true

else

puts "高い低い正解のみで答える。"

end

end

  

if found

puts "メッセージを入力してください！"

message = gets.to_s

puts "ゲームが終了しました！#{message}"

puts "あなたの年齢は#{guess}歳ですね！"

exit

else

puts "その年齢は範囲内にないようです。"

exit

end
```
