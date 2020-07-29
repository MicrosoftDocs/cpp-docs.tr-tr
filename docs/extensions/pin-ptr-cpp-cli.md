---
title: pin_ptr (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
ms.openlocfilehash: 9a9144229b75c09a892ddbf5bd592e67c7c2b6d9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230564"
---
# <a name="pin_ptr-ccli"></a>pin_ptr (C++/CLI)

Yalnızca ortak dil çalışma zamanı ile kullanılan *sabitleme işaretçisini*bildirir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliği için tüm çalışma zamanları için uygulanan bir açıklama yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliği Windows Çalışma Zamanı desteklenmez.)

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

*Sabitleme işaretçisi* , nesne işaret eden atık toplanan yığında taşınmasını engelleyen iç bir işaretçidir. Diğer bir deyişle, Sabitleme işaretçisinin değeri ortak dil çalışma zamanı tarafından değiştirilmez. Yönetilmeyen işlev çağrısının çözümlenmesi sırasında adresin beklenmedik şekilde değişmemesi için, yönetilen bir sınıfın adresini yönetilmeyen bir işleve geçirdiğinizde bu gereklidir.

### <a name="syntax"></a>Söz dizimi

```cpp
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;
```

### <a name="parameters"></a>Parametreler

*cv_qualifier*<br/>
**`const`** veya **`volatile`** niteleyicileri. Varsayılan olarak sabitleme işaretçisi olur **`volatile`** . Yok ancak sabitleme işaretçisi bildirmek için bir hata değildir **`volatile`** .

*türüyle*<br/>
*Başlatıcı*türü.

*l*<br/>
**Pin_ptr** değişkeninin adı.

*izer*<br/>
Bir başvuru türünün üyesi, yönetilen bir dizinin öğesi ya da yerel bir işaretçiye atayabileceğiniz başka herhangi bir nesne.

### <a name="remarks"></a>Açıklamalar

**Pin_ptr** , yerel işaretçinin işlevselliğinin bir üst kümesini temsil eder. Bu nedenle, yerel bir işaretçiye atanabilecek her türlü şey bir **pin_ptr**da atanabilir. İç işaretçiye karşılaştırma ve işaretçi aritmetiği dahil olmak üzere yerel işaretçilerle aynı işlem kümesi gerçekleştirmesine izin verilir.

Yönetilen bir sınıfın bir nesnesi veya alt nesnesi sabitlenebilir ve bu durumda ortak dil çalışma zamanı atık toplama sırasında taşınamaz. Bunun asıl kullanımı, yönetilmeyen bir işlev çağrısının gerçek parametresi olarak yönetilen verilere bir işaretçi geçirmektir. Bir koleksiyon çevrimi sırasında, çalışma zamanı sabitleme işaretçisi için oluşturulan meta verileri inceler ve işaret ettiği öğeyi taşımaz.

Bir nesnenin sabitlenmesi Ayrıca değer alanlarını da sabitler; diğer bir deyişle, ilkel veya değer türünün alanları. Ancak, izleme tutamacı () tarafından belirtilen alanlar `%` sabitlenmez.

Yönetilen bir nesnede tanımlanan bir alt nesnenin sabitlenmesi, tüm nesnenin sabitlenmesini etkiler.

Sabitleme işaretçisi yeni bir değere işaret etmek için yeniden atandığında, işaret edilen önceki örnek artık sabitlenmiş olarak kabul edilmez.

Bir nesne yalnızca bir **pin_ptr** işaret edilirken sabitlenmiştir. Sabitleme işaretçisi kapsam dışına geçtiğinde nesne artık sabitlenemez veya [nullptr](nullptr-cpp-component-extensions.md)olarak ayarlanır. **Pin_ptr** kapsam dışına çıktıktan sonra, sabitlenmiş nesne çöp toplayıcı tarafından yığında taşınabilir. Hala nesneyi işaret eden yerel işaretçiler güncellenmez ve bunlardan birine başvurulmaz kurtarılamaz bir özel durum oluşturabilir.

Nesneye sabitleme işaretçileri yoksa (tüm sabitleme işaretçileri kapsam dışına çıktı, diğer nesneleri işaret etmek için [yeniden atandı, ya da kendisine atandı](nullptr-cpp-component-extensions.md)), nesnenin sabitlenmiş olmaması garanti edilir.

Sabitleme işaretçisi bir başvuru tanıtıcısı, değer türü veya paketlenmiş tür tanıtıcısı, yönetilen bir türün üyesi veya yönetilen dizinin bir öğesi ile işaret edebilir. Başvuru türüne işaret edemez.

Yerel bir nesneye işaret eden bir **pin_ptr** adresini almak tanımsız davranışlara neden olur.

Sabitleme işaretçileri yığında yalnızca statik olmayan yerel değişkenler olarak bildirilemez.

Sabitleme işaretçileri şu şekilde kullanılamaz:

- işlev parametreleri

- bir işlevin dönüş türü

- bir sınıfın üyesi

- bir tür dönüştürmenin hedef türü.

**pin_ptr** `cli` ad alanıdır. Daha fazla bilgi için bkz. [Platform, Default ve CLI ad alanları](platform-default-and-cli-namespaces-cpp-component-extensions.md).

İç işaretçiler hakkında daha fazla bilgi için bkz. [interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md).

İşaretçileri sabitleme hakkında daha fazla bilgi için bkz. [nasıl yapılır: işaretçi ve dizileri sabitleme](how-to-pin-pointers-and-arrays.md) ve [nasıl yapılır: sabitleme Işaretçileri ve değer türleri bildirme](how-to-declare-pinning-pointers-and-value-types.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, bir dizinin ilk öğesinin konumunu kısıtlamak için **pin_ptr** kullanır.

```cpp
// pin_ptr_1.cpp
// compile with: /clr
using namespace System;
#define SIZE 10

#pragma unmanaged
// native function that initializes an array
void native_function(int* p) {
   for(int i = 0 ; i < 10 ; i++)
    p[i] = i;
}
#pragma managed

public ref class A {
private:
   array<int>^ arr;   // CLR integer array

public:
   A() {
      arr = gcnew array<int>(SIZE);
   }

   void load() {
   pin_ptr<int> p = &arr[0];   // pin pointer to first element in arr
   int* np = p;   // pointer to the first element in arr
   native_function(np);   // pass pointer to native function
   }

   int sum() {
      int total = 0;
      for (int i = 0 ; i < SIZE ; i++)
         total += arr[i];
      return total;
   }
};

int main() {
   A^ a = gcnew A;
   a->load();   // initialize managed array using the native function
   Console::WriteLine(a->sum());
}
```

```Output
45
```

Aşağıdaki örnek, bir iç işaretçinin sabitleme işaretçisine dönüştürüleceğini ve adres işlecinin () dönüş türünün, `&` işlenen yönetilen yığında olduğunda iç işaretçi olduğunu gösterir.

```cpp
// pin_ptr_2.cpp
// compile with: /clr
using namespace System;

ref struct G {
   G() : i(1) {}
   int i;
};

ref struct H {
   H() : j(2) {}
   int j;
};

int main() {
   G ^ g = gcnew G;   // g is a whole reference object pointer
   H ^ h = gcnew H;

   interior_ptr<int> l = &(g->i);   // l is interior pointer

   pin_ptr<int> k = &(h->j);   // k is a pinning interior pointer

   k = l;   // ok
   Console::WriteLine(*k);
};
```

```Output
1
```

Aşağıdaki örnek, Sabitleme işaretçisinin başka bir türe yayınlanacağını göstermektedir.

```cpp
// pin_ptr_3.cpp
// compile with: /clr
using namespace System;

ref class ManagedType {
public:
   int i;
};

int main() {
   ManagedType ^mt = gcnew ManagedType;
   pin_ptr<int> pt = &mt->i;
   *pt = 8;
   Console::WriteLine(mt->i);

   char *pc = ( char* ) pt;
   *pc = 255;
   Console::WriteLine(mt->i);
}
```

```Output
8
255
```
