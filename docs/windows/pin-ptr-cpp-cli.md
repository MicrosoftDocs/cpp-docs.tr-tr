---
title: pin_ptr (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- pin_ptr_cpp
- stdcli::language::pin_ptr
- pin_ptr
dev_langs:
- C++
helpviewer_keywords:
- pinning pointers
- pin_ptr keyword [C++]
ms.assetid: 6c2e6c73-4ec2-4dce-8e1f-ccf3a9f9d0aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de7f4c94ec0d9cb5a9a57315ebda015b7737132c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392768"
---
# <a name="pinptr-ccli"></a>pin_ptr (C++/CLI)

Bildiren bir *sabitleme işaretçisi*, yalnızca ortak dil çalışma zamanı ile kullanılır.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliğinin tüm çalışma zamanları için geçerli olan açıklaması yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliği, Windows çalışma zamanı'nda desteklenmiyor.)

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

A *sabitleme işaretçisi* nesne engelleyen bir işaretçiye atık toplanan yığında taşınmasını verilir. Diğer bir deyişle, bir sabitleme işaretçisi değeri, ortak dil çalışma zamanı tarafından değiştirilmez. Adresi yönetilmeyen bir işlev çağrısının bir Çözümleme sırasında beklenmedik bir şekilde değiştirmez, yönetilen bir sınıf adresi yönetilmeyen bir işleve geçirdiğinizde, bu gereklidir.

### <a name="syntax"></a>Sözdizimi

```cpp
[cli::]pin_ptr<cv_qualifiertype>var = &initializer;
```

### <a name="parameters"></a>Parametreler

*cv_qualifier*<br/>
**const** veya **geçici** niteleyicileri. Varsayılan olarak, bir sabitleme işaretçisi olan **geçici**. Bir sabitleme işaretçisi bildirmek için bir hatayı değil gereksizdir **geçici**.

*Türü*<br/>
Türünü *Başlatıcı*.

*var*<br/>
Adını **pin_ptr** değişkeni.

*Başlatıcı*<br/>
Bir başvuru türü, yönetilen bir diziyi veya yerel bir işaretçiye atayabilirsiniz herhangi bir nesne öğesi üyesi.

### <a name="remarks"></a>Açıklamalar

A **pin_ptr** yerel bir işaretçi bir işlevselliğin temsil eder. Bu nedenle, yerel bir işaretçiye atanabilir herhangi bir şey de atanabilir bir **pin_ptr**. İç işaretçiye karşılaştırma ve işaretçi aritmetiğini dahil olmak üzere, yerel işaretçiler olarak aynı işlemleri kümesini gerçekleştirmek için izin verilir.

Bir nesne veya alt nesne bir yönetilen sınıfın durumda ortak dil çalışma zamanı, çöp toplama sırasında taşımaz sabitlenebilir. Bu asıl kullanımı, yönetilmeyen işlev çağrısının gerçek bir parametre olarak yönetilen verileri bir işaretçi geçirmektir. Bir toplama döngüsü sırasında çalışma zamanı için sabitleme işaretçisi oluşturulan meta verileri incelemek ve işaret öğe taşınmaz.

Bir nesneyi sabitleme değeri alanlarını sabitler; diğer bir deyişle, temel alanlarını veya değer türü. Ancak, alanlar bildirilen izleme işleyicisi tarafından (`%`) değil sabitlenir.

Yönetilen bir nesnenin içinde tanımlanmış bir alt nesneyi sabitleme tüm nesne sabitlenmesi etkisi vardır.

Sabitleme işaretçisi için yeni bir değer işaret edecek şekilde yeniden atandı, işaret önceki örneği artık değerlendirilir sabitlenebilir.

Bir nesne sabitlenmiş ancak bir **pin_ptr** kendisine işaret eder. Nesne artık onun sabitleme işaretçisi kapsamın dışına çıkıncaya ya da ayarlanmış sabitlenmiş [nullptr](../windows/nullptr-cpp-component-extensions.md). Sonra **pin_ptr** sabitlenmiş nesne kapsam dışına gider taşınabilir yığınında çöp toplayıcısı tarafından. Hala nesneye işaret eden herhangi bir yerel işaretçilerle güncelleştirilmez ve bunlardan birinin XML'deki başvuran kurtarılamaz bir özel durum oluşturabilen.

Hiçbir sabitleme işaretçileri nesneye gelirseniz (kapsam dışına oluştu, diğer nesnelere işaret edecek şekilde yeniden veya atanmış olan tüm sabitleme işaretçileri [nullptr](../windows/nullptr-cpp-component-extensions.md)), nesne olmayan sabitlenmiş garanti edilir.

Bir sabitleme işaretçisi bir başvuru tanıtıcı, değer türü veya kutulu tür tanıtıcı, bir yönetilen türün üye veya yönetilen bir dizi öğesi işaret edebilir. Bu, bir başvuru türüne işaret edemez.

Adresinin alınmasına bir **pin_ptr** yerel nesnesini noktalarına tanımsız davranışa neden.

Sabitleme işaretçileri yığında yalnızca statik olmayan yerel değişkenleri olarak bildirilebilir.

Sabitleme işaretçileri olarak kullanılamaz:

- işlev parametreleri

- bir işlevin dönüş türü

- bir sınıf üyesi

- bir yayın hedef türü.

**pin_ptr** bulunduğu `cli` ad alanı. Daha fazla bilgi için [Platform, varsayılan ve cli ad alanları](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).

İç işaretçiler hakkında daha fazla bilgi için bkz: [interior_ptr (C + +/ CLI)](../windows/interior-ptr-cpp-cli.md).

İşaretçileri sabitleme hakkında daha fazla bilgi için bkz. [nasıl yapılır: PIN işaretçiler ve dizileri](../windows/how-to-pin-pointers-and-arrays.md) ve [nasıl yapılır: sabitleme işaretçileri bildirmek ve değer türleri](../windows/how-to-declare-pinning-pointers-and-value-types.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnekte **pin_ptr** kısıtlayan bir dizinin ilk öğenin konumu.

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

Aşağıdaki örnek, iç işaretçiye bir sabitleme işaretçisine dönüştürülebilir ve sonuç address-of işlecini türü gösterir (`&`) işlenen yönetilen yığında iç işaretçiye olur.

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

Aşağıdaki örnek, bir sabitleme işaretçisi başka bir türüne dönüştürülebilen gösterir.

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