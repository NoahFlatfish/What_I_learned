# each와의 차이는?

단순 each와 비교해서 index번호를 부여해준다.

# each_with_index와each.with_index의 차이는?

each_with_index는 고정으로 인덴스번호를 0부터 부여하지만 each.with_index는 시작하는 인덱스번호를 지정가능하다.

# each_with_index 예제

```
array = ["sana", "dahyun", "jihyo"]
array.each_with_index do |element, index|
  p "#{index}：#{element}"
end
```

#### result:

```
"0：sana"
"1：dahyun"
"2：jihyo"
```

# each.with_index 예제

```
array = ["sana", "dahyun", "jihyo"]
array.each.with_index(1) do |element, index|
  p "#{index}：#{element}"
end
```

#### result:

```rails
"1：sana"
"2：dahyun"
"3：jihyo"
```

