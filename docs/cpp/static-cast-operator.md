---
title: static_cast İşleci
ms.date: 11/04/2016
f1_keywords:
- static_cast_cpp
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
ms.openlocfilehash: 37708bf50b28eb120af8e8a79e770c3121e6f509
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178593"
---
# <a name="static_cast-operator"></a>static_cast İşleci

*İfadeyi* yalnızca ifadede bulunan türlere göre *tür kimliği* türüne dönüştürür.

## <a name="syntax"></a>Sözdizimi

```
static_cast <type-id> ( expression )
```

## <a name="remarks"></a>Açıklamalar

Standart C++ kapsamında, dönüştürmenin güvenliğini sağlamaya yardımcı olmak için bir çalışma zamanı tür denetimi yapılmaz. C++/CX kapsamında, derleme zamanı ve çalışma zamanı denetimi gerçekleştirilir. Daha fazla bilgi için bkz. [atama](casting.md).

**Static_cast** işleci, bir işaretçiyi taban sınıfına türetilmiş bir sınıfa bir işaretçiye dönüştürme gibi işlemler için kullanılabilir. Bu tür dönüştürmeler her zaman güvenli değildir.

Genel olarak, numaralandırmalar gibi sayısal veri türlerini yukarı ve aşağı kaylar halinde dönüştürmek istediğinizde **static_cast** kullanırsınız ve dönüştürmeye dahil olan veri türlerinden emin olursunuz. **static_cast** dönüştürmeleri **dynamic_cast** dönüştürmeleri kadar güvenli değildir, çünkü **static_cast** hiçbir çalışma zamanı tür denetimi yapmaz, **dynamic_cast** sırasında. Belirsiz bir işaretçiye **dynamic_cast** başarısız olur, ancak bir **static_cast** yanlış bir değer olmadığı gibi döndürülür; Bu tehlikeli olabilir. **Dynamic_cast** dönüştürmeleri daha güvenli olsa da, **dynamic_cast** yalnızca işaretçiler veya başvurular üzerinde çalışır ve çalışma zamanı tür denetimi bir ek yüktür. Daha fazla bilgi için bkz. [dynamic_cast işleci](../cpp/dynamic-cast-operator.md).

Aşağıdaki örnekte satır `D* pd2 = static_cast<D*>(pb);` güvenli değildir, çünkü `D` `B`olmayan alanlar ve yöntemlere sahip olabilir. Ancak, `D` her zaman tüm `B`içerdiği için satır `B* pb2 = static_cast<B*>(pd);` güvenli bir dönüştürmedir.

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

[Dynamic_cast](../cpp/dynamic-cast-operator.md)aksine, `pb`**static_cast** dönüştürmesi üzerinde hiçbir çalışma zamanı denetimi yapılmaz. `pb` tarafından işaret edilen nesne `D`türünde bir nesne olmayabilir, bu durumda `*pd2` kullanımı felaket olabilir. Örneğin, `D` sınıfının üyesi olan, ancak `B` sınıfı olmayan bir işlevi çağırmak, erişim ihlaline neden olabilir.

**Dynamic_cast** ve **static_cast** işleçleri bir işaretçiyi bir sınıf hiyerarşisi boyunca taşır. Ancak **static_cast** , özel olarak cast ifadesinde belirtilen bilgilere bağımlıdır ve bu nedenle güvenli olmayabilir. Örneğin:

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

`pb` gerçekten `D`türündeki bir nesneye işaret ediyorsa, `pd1` ve `pd2` aynı değeri alır. `pb == 0`aynı değeri de alır.

`pb`, tüm `D` sınıfına değil `B` türünde bir nesneye işaret ediyorsa, **dynamic_cast** sıfır döndürmek için yeterince haberdar olur. Ancak, **static_cast** `pb` programcı onayını kullanır ve bu, `D` türünde bir nesneye işaret eder ve yalnızca bu beklenen `D` nesnesine bir işaretçi döndürür.

Sonuç olarak, **static_cast** örtük dönüştürmelerin tersini yapabilir, bu durumda sonuçlar tanımsız olur. **Static_cast** dönüştürmenin sonuçlarının güvenli olduğunu doğrulamak için programcıya kalmıştır.

Bu davranış, sınıf türleri dışındaki türler için de geçerlidir. Örneğin, **static_cast** bir int 'ten **char**'a dönüştürmek için kullanılabilir. Ancak, sonuçta elde edilen **char** , tüm **int** değerini tutacak kadar bitmeyebilir. Ayrıca, bir **static_cast** dönüştürmenin sonuçlarının güvenli olduğunu doğrulamak için programcıda kalır.

**Static_cast** işleci, standart dönüşümler ve Kullanıcı tanımlı dönüştürmeler de dahil olmak üzere herhangi bir örtük dönüştürmeyi gerçekleştirmek için de kullanılabilir. Örneğin:

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

**Static_cast** işleci, tam olarak bir integral değeri bir numaralandırma türüne dönüştürebilir. Tamsayı türünün değeri, numaralandırma değerleri aralığı içinde kalmıyorsa, sonuç olarak elde edilen numaralandırma değeri tanımsızdır.

**Static_cast** işleci, null işaretçi değerini hedef türün null işaretçi değerine dönüştürür.

Herhangi bir ifade, **static_cast** işleci tarafından void türüne açıkça dönüştürülebilir. Hedef void türü, isteğe bağlı olarak **const**, **volatile**veya **__unaligned** özniteliğini içerebilir.

**Static_cast** işleci **const**, **volatile**veya **__unaligned** özniteliklerinin üzerine atanamaz. Bu öznitelikleri kaldırma hakkında bilgi için bkz. [Const_cast işleci](../cpp/const-cast-operator.md) .

**C++/CLI:** Bir yeniden konumlandırma Atık toplayıcısının üzerinde denetlenmeyen kayıtları gerçekleştirmeye yönelik tehlike, **static_cast** kullanımı, doğru şekilde çalışacağından emin olduğunuzda yalnızca performans açısından kritik kodda olmalıdır. Yayın modunda **static_cast** kullanmanız gerekiyorsa, başarılı olduğundan emin olmak için hata ayıklama derlemelerinizi [safe_cast](../extensions/safe-cast-cpp-component-extensions.md) ile değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

[Atama İşleçleri](../cpp/casting-operators.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
