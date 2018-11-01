---
title: Referans Türleri için C++ Yığın Anlamları
ms.date: 11/04/2016
helpviewer_keywords:
- reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
ms.openlocfilehash: b2d2d5991f7b52727b366214b8ca9ed4d8e14956
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607872"
---
# <a name="c-stack-semantics-for-reference-types"></a>Referans Türleri için C++ Yığın Anlamları

Visual C++ 2005'ten önce bir başvuru türünün bir örneği yalnızca kullanarak oluşturulabilir `new` toplanan yığın atık nesneyi oluşturan işleci. Bununla birlikte, artık yığında yerel türünün örneğini oluşturmak için kullanacağınız aynı sözdizimini kullanarak bir başvuru türünün bir örneğini oluşturabilirsiniz. Bu nedenle, kullanın gerekmez [yeni başvuru, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) başvuru türünde bir nesne oluşturmak için. Ve nesne kapsam dışına çıktığında, derleyicinin nesnenin yok Edicisi çağırır.

## <a name="remarks"></a>Açıklamalar

Yığın anlamları kullanarak bir başvuru türünün örneğini oluşturmak, derleyici dahili olarak örnek atık toplanan yığında oluşturun (kullanarak `gcnew`).

Bir işlev imzası veya dönüş türü bir değere göre başvuru türünde bir örnek içerdiğinde, işlevi meta veriler (ile modreq) özel işlem gerektiren olarak işaretlenir. Bu özel işlem şu anda olan Visual C++ istemciler tarafından; yalnızca sağlanan Diğer diller, alıcı işlevleri veya yığın anlamları ile oluşturulan başvuru türleri kullanan veri şu anda desteklemez.

Kullanmak için bir neden `gcnew` (dinamik ayırma) yığını yerine türü yok yok Edicisi varsa semantiği olacaktır. Ayrıca, yığın anlamları işlevi imzalarında ile oluşturulan başvuru türlerini kullanarak Visual C++ dışındaki diller tarafından tüketilmesi işlevlerinizi istiyorsanız mümkün olmaz.

Derleyici, bir başvuru türü için bir kopya Oluşturucu oluşturmaz. Bu nedenle, bir değere göre başvuru türü imzada kullanan bir işlev tanımlarsanız, başvuru türü için bir kopya Oluşturucu tanımlamanız gerekir. Bir başvuru türü için bir kopya Oluşturucu bir imza aşağıdaki biçime sahiptir: `R(R%){}`.

Derleyicinin bir varsayılan atama işleci bir başvuru türü için oluşturmaz. Atama işleci, yığın anlamları kullanarak bir nesne oluşturun ve yığın anlamları kullanarak oluşturduğunuz var olan bir nesne ile başlatmak sağlar. Bir atama işleci bir başvuru türü için bir imza aşağıdaki biçime sahiptir: `void operator=( R% ){}`.

Türün yok Edicisi kritik kaynakları serbest bırakır ve başvuru türleri için yığın anlamları kullanırsanız yok ediciyi açıkça çağırmak gerekmez (veya çağrı `delete`). Başvuru türlerindeki Yıkıcılar hakkında daha fazla bilgi için bkz. [yok ediciler ve sonlandırıcılar, nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Derleyici tarafından üretilen atama işleci aşağıdaki eklemelerle normal standart C++ kurallarını izler:

- Üyeleri bir başvuru türü için bir tanıtıcı türü olan herhangi bir statik olmayan veri kopyalanan (bir işaretçi türü olan bir statik olmayan veri üyesi gibi kabul edilir) basit.

- Değer türü bir basit türü olan herhangi bir statik olmayan veri üyesi kopyalanır.

- Bir başvuru türünün bir örneği, türü olan herhangi bir statik olmayan veri üyesi başvuru türün kopya oluşturucu çağrısı çağırır.

Derleyici ayrıca sağlar bir `%` birli işleç, temel alınan tanıtıcı türü için yığın anlamları kullanılarak oluşturulan bir başvuru türünün bir örneği dönüştürülecek.

Yığın anlamları ile kullanmak için aşağıdaki başvuru türleri kullanılamıyor:

- [temsilci (C++ Bileşen Uzantıları)](../windows/delegate-cpp-component-extensions.md)

- [Diziler](../windows/arrays-cpp-component-extensions.md)

- <xref:System.String>

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki kod örneği, başvuru türleri için yığın anlamları örneklerini bildirmek gösterilmektedir nasıl atama işleci ve kopya Oluşturucusu çalışır ve yığın anlamları kullanılarak oluşturulan başvuru türü ile nasıl bir izleme başvurusu.

### <a name="code"></a>Kod

```cpp
// stack_semantics_for_reference_types.cpp
// compile with: /clr
ref class R {
public:
   int i;
   R(){}

   // assignment operator
   void operator=(R% r) {
      i = r.i;
   }

   // copy constructor
   R(R% r) : i(r.i) {}
};

void Test(R r) {}   // requires copy constructor

int main() {
   R r1;
   r1.i = 98;

   R r2(r1);   // requires copy constructor
   System::Console::WriteLine(r1.i);
   System::Console::WriteLine(r2.i);

   // use % unary operator to convert instance using stack semantics
   // to its underlying handle
   R ^ r3 = %r1;
   System::Console::WriteLine(r3->i);

   Test(r1);

   R r4;
   R r5;
   r5.i = 13;
   r4 = r5;   // requires a user-defined assignment operator
   System::Console::WriteLine(r4.i);

   // initialize tracking reference
   R % r6 = r4;
   System::Console::WriteLine(r6.i);
}
```

### <a name="output"></a>Çıkış

```Output
98
98
98
13
13
```

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)