---
description: Static_cast Işleci hakkında daha fazla bilgi edinin
title: static_cast İşleci
ms.date: 11/04/2016
f1_keywords:
- static_cast_cpp
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
ms.openlocfilehash: 7d76b4e21adea6561d7d6822871631c242aaf9c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317967"
---
# <a name="static_cast-operator"></a>static_cast İşleci

*İfadeyi* yalnızca ifadede bulunan türlere göre *tür kimliği* türüne dönüştürür.

## <a name="syntax"></a>Syntax

```
static_cast <type-id> ( expression )
```

## <a name="remarks"></a>Açıklamalar

Standart C++ kapsamında, dönüştürmenin güvenliğini sağlamaya yardımcı olmak için bir çalışma zamanı tür denetimi yapılmaz. C++/CX kapsamında, derleme zamanı ve çalışma zamanı denetimi gerçekleştirilir. Daha fazla bilgi için bkz. [atama](casting.md).

İşleci, bir **`static_cast`** işaretçiyi taban sınıfına türetilmiş bir sınıfa olan işaretçiye dönüştürme gibi işlemler için kullanılabilir. Bu tür dönüştürmeler her zaman güvenli değildir.

Genel olarak **`static_cast`** , numaralandırmalar gibi sayısal veri türlerini yukarı ve aşağı kaylar halinde dönüştürmek istediğinizde ve dönüştürmeye dahil olan veri türlerinden emin olmanız durumunda kullanırsınız. **`static_cast`** dönüşümler, **`dynamic_cast`** **`static_cast`** çalışma zamanı tür denetimi olmadığından, dönüştürme olarak güvenli değildir **`dynamic_cast`** . **`dynamic_cast`** Belirsiz bir işaretçi başarısız olur, ancak **`static_cast`** hiçbir şey yanlış gibi bir değer döndürür; bu tehlikeli olabilir. **`dynamic_cast`** Dönüşümler daha güvenli olsa da, **`dynamic_cast`** yalnızca işaretçiler veya başvurular üzerinde çalışır ve çalışma zamanı tür denetimi bir ek yüktür. Daha fazla bilgi için bkz. [dynamic_cast işleci](../cpp/dynamic-cast-operator.md).

Aşağıdaki örnekte, satır `D* pd2 = static_cast<D*>(pb);` güvenli değildir çünkü `D` içinde olmayan alanlar ve yöntemler olabilir `B` . Ancak, `B* pb2 = static_cast<B*>(pd);` her zaman tüm ' ı içerdiğinden, satır güvenli bir dönüştürmedir `D` `B` .

```cpp
// static_cast_Operator.cpp
// compile with: /LD
class B {};

class D : public B {};

void f(B* pb, D* pd) {
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields
                                   // and methods that are not in B.

   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always
                                   // contains all of B.
}
```

[Dynamic_cast](../cpp/dynamic-cast-operator.md)aksine, dönüştürülürken hiçbir çalışma zamanı denetimi yapılmaz **`static_cast`** `pb` . Tarafından işaret `pb` edilen nesne, türünde bir nesne olmayabilir `D` , bu durumda, `*pd2` felaket olabilir. Örneğin, sınıfının bir üyesi olan `D` , ancak sınıfı olmayan bir işlevi çağırmak `B` , erişim ihlaline yol açabilir.

**`dynamic_cast`** Ve **`static_cast`** işleçleri bir işaretçiyi bir sınıf hiyerarşisi boyunca taşır. Ancak, **`static_cast`** yalnızca cast ifadesinde belirtilen bilgilere güvenir ve bu nedenle güvenli olmayabilir. Örneğin:

```cpp
// static_cast_Operator_2.cpp
// compile with: /LD /GR
class B {
public:
   virtual void Test(){}
};
class D : public B {};

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);
   D* pd2 = static_cast<D*>(pb);
}
```

`pb`Gerçekten türü bir nesneye işaret ediyorsa `D` , `pd1` ve `pd2` aynı değere sahip olur. Ayrıca, varsa aynı değeri alırlar `pb == 0` .

, `pb` Türü bir nesneye işaret ediyorsa `B` ve tüm `D` sınıfa değil, **`dynamic_cast`** sıfır döndürmek için yeterince haberdar olur. Ancak, **`static_cast`** Programcının bir nesne türünü işaret eden onaylama onayını kullanır `pb` `D` ve yalnızca bu beklenen nesneye bir işaretçi döndürür `D` .

Sonuç olarak, **`static_cast`** örtük dönüştürmelerin tersini yapabilir, bu durumda sonuçlar tanımsız olur. Dönüştürme sonuçlarının güvenli olduğunu doğrulamak için programcıya kalmıştır **`static_cast`** .

Bu davranış, sınıf türleri dışındaki türler için de geçerlidir. Örneğin, bir **`static_cast`** int 'den a 'ya dönüştürmek için kullanılabilir **`char`** . Ancak, sonuçta elde edilen **`char`** tüm değeri tutacak yeterli bit olmayabilir **`int`** . Bu, bir dönüştürmenin sonuçlarının güvenli olduğunu doğrulamak için programcıda kalır **`static_cast`** .

**`static_cast`** İşleci, standart dönüşümler ve Kullanıcı tanımlı dönüştürmeler de dahil olmak üzere herhangi bir örtük dönüştürmeyi gerçekleştirmek için de kullanılabilir. Örneğin:

```cpp
// static_cast_Operator_3.cpp
// compile with: /LD /GR
typedef unsigned char BYTE;

void f() {
   char ch;
   int i = 65;
   float f = 2.5;
   double dbl;

   ch = static_cast<char>(i);   // int to char
   dbl = static_cast<double>(f);   // float to double
   i = static_cast<BYTE>(ch);
}
```

**`static_cast`** İşleci, tam olarak bir tamsayı değerini bir numaralandırma türüne dönüştürebilir. Tamsayı türünün değeri, numaralandırma değerleri aralığı içinde kalmıyorsa, sonuç olarak elde edilen numaralandırma değeri tanımsızdır.

**`static_cast`** İşleç, null işaretçi değerini hedef türün null işaretçi değerine dönüştürür.

Any ifadesi işleci tarafından void türüne açıkça dönüştürülebilir **`static_cast`** . Hedef void türü, isteğe bağlı olarak **`const`** , **`volatile`** , veya **`__unaligned`** özniteliğini içerebilir.

**`static_cast`** İşleç **`const`** , **`volatile`** , veya **`__unaligned`** özniteliklerini alamaz. Bu öznitelikleri kaldırma hakkında bilgi için bkz. [Const_cast işleci](../cpp/const-cast-operator.md) .

**C++/CLI:** Bir yeniden konumlandırma Atık toplayıcısının üzerinde denetlenmeyen kayıtları gerçekleştirmeye yönelik tehlike, ' ın kullanılması, **`static_cast`** doğru şekilde çalışacağından emin olduğunuzda yalnızca performans açısından kritik kodda olmalıdır. Yayın modunda kullanmanız gerekiyorsa **`static_cast`** , başarılı olduğundan emin olmak için hata ayıklama derlemelerinizi [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

[Atama Işleçleri](../cpp/casting-operators.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
