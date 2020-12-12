---
description: 'Hakkında daha fazla bilgi edinin: başvuru türleri için C++ yığın semantiği'
title: Referans Türleri için C++ Yığın Anlamları
ms.date: 11/04/2016
helpviewer_keywords:
- reference types, C++ stack semantics for
ms.assetid: 319a1304-f4a4-4079-8b84-01cec847d531
ms.openlocfilehash: a7f377225e70eff4093d4b9820a3d14644b96f58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124325"
---
# <a name="c-stack-semantics-for-reference-types"></a>Referans Türleri için C++ Yığın Anlamları

Visual Studio 2005 ' den önce, başvuru türünün bir örneği yalnızca, **`new`** atık toplanan yığında nesneyi oluşturan işleci kullanılarak oluşturulabilir. Bununla birlikte, artık yığında yerel bir türün örneğini oluşturmak için kullandığınız söz dizimini kullanarak başvuru türünün bir örneğini oluşturabilirsiniz. Bu nedenle, başvuru türünde bir nesne oluşturmak için [Yeni ref, gcnew](../extensions/ref-new-gcnew-cpp-component-extensions.md) kullanmanız gerekmez. Nesne kapsam dışına geçtiğinde, derleyici nesnenin yıkıcıyı çağırır.

## <a name="remarks"></a>Açıklamalar

Yığın semantiğini kullanarak bir başvuru türü örneği oluşturduğunuzda, derleyici örneği atık toplanan yığında (kullanarak) dahili olarak oluşturur **`gcnew`** .

Bir işlevin imzası veya dönüş türü, değer bir başvuru türünün bir örneğini içerdiğinde, bu işlev meta verilerde özel işleme (modreq ile) göre işaretlenir. Bu özel işleme Şu anda yalnızca Visual C++ istemcileri tarafından sağlanır; diğer diller şu anda, yığın semantiğinin oluşturduğu başvuru türlerini kullanan işlevleri veya verileri kullanmayı desteklememektedir.

**`gcnew`** Tür yok edicisi yoksa yığın semantiği yerine kullanmanın bir nedeni (dinamik ayırma) olur. Ayrıca, işlevlerinizin Visual C++ dışındaki diller tarafından kullanılmasını istiyorsanız işlev imzalarında yığın semantiğinin kullanıldığı başvuru türlerini kullanmak mümkün olmaz.

Derleyici, bir başvuru türü için kopya Oluşturucusu oluşturmaz. Bu nedenle, İmzada değere göre başvuru türü kullanan bir işlev tanımlarsanız, başvuru türü için bir kopya Oluşturucu tanımlamanız gerekir. Bir başvuru türü için kopya Oluşturucu aşağıdaki biçimde bir imzaya sahip: `R(R%){}` .

Derleyici, bir başvuru türü için varsayılan atama işleci oluşturmaz. Atama işleci, yığın semantiğini kullanarak bir nesne oluşturmanıza ve yığın semantiğini kullanarak oluşturulan mevcut bir nesneyle başlatmanıza olanak tanır. Bir başvuru türü için atama işleci aşağıdaki biçimde bir imzaya sahip: `void operator=( R% ){}` .

Türün yıkıcısı kritik kaynaklar yayımlarsa ve başvuru türleri için yığın semantiğini kullanıyorsanız, yıkıcıyı (veya çağrısını) açıkça çağırmanız gerekmez **`delete`** . Başvuru türlerindeki yok ediciler hakkında daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Derleyici tarafından oluşturulan atama operatörü, aşağıdaki eklemelerle olağan standart C++ kurallarını izler:

- Türü bir başvuru türüne yönelik tanıtıcı olan statik olmayan veri üyeleri, basit bir şekilde kopyalanır (türü işaretçi olan statik olmayan bir veri üyesi olarak işlenir).

- Türü bir değer türü olan statik olmayan herhangi bir veri üyesi, yüzeysel olarak kopyalanabilir.

- Türü bir başvuru türünün örneği olan statik olmayan herhangi bir veri üyesi, başvuru türünün kopya oluşturucusuna bir çağrı çağıracaktır.

Derleyici Ayrıca, `%` yığın semantiği kullanılarak oluşturulan bir başvuru türünün örneğini temel alınan tanıtıcı türüne dönüştürmek için birli bir operatör sağlar.

Aşağıdaki başvuru türleri yığın semantiğinin kullanımına açık değil:

- [temsilci (C++ Bileşen Uzantıları)](../extensions/delegate-cpp-component-extensions.md)

- [Diziler](../extensions/arrays-cpp-component-extensions.md)

- <xref:System.String>

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki kod örneği, dizi semantiğine sahip başvuru türleri örneklerinin nasıl bildirilemeyeceğini, atama işlecinin ve kopya oluşturucusunun nasıl çalıştığını ve yığın semantiği kullanılarak oluşturulan başvuru türü ile izleme başvurusunun nasıl başlatılacağını gösterir.

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

### <a name="output"></a>Çıktı

```Output
98
98
98
13
13
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)
