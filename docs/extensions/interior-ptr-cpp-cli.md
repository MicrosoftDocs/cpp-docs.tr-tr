---
title: interior_ptr (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- stdcli::language::interior_ptr
- interior_ptr_cpp
- interior_ptr
helpviewer_keywords:
- interior_ptr keyword [C++]
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
ms.openlocfilehash: 0fba04efeaa634f5e21600768297aee0d999d1c6
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028327"
---
# <a name="interiorptr-ccli"></a>interior_ptr (C++/CLI)

Bir *işaretçiye* bir başvuru türü içinde ancak nesnenin kendisi için bir işaretçiyi bildirir. İç işaretçi, başvuru tanıtıcı, değer türü, Kutulu tür tanıtıcı, bir yönetilen türün üye veya yönetilen bir dizinin bir öğesine işaret edebilir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliğinin tüm çalışma zamanları için geçerli olan açıklaması yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliğinin yalnızca Windows çalışma zamanı için geçerli olan açıklaması yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Aşağıdaki sözdizimi örneği iç işaretçiye gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::interior_ptr<cv_qualifier type> var = &initializer;
```

### <a name="parameters"></a>Parametreler

*cv_qualifier*<br/>
**const** veya **geçici** niteleyicileri.

* türü*<br/>
Türünü *Başlatıcı*.

*var*<br/>
Adını **interior_ptr** değişkeni.

*Başlatıcı*<br/>
Bir başvuru türü, yönetilen bir diziyi veya yerel bir işaretçiye atayabilirsiniz herhangi bir nesne öğesi üyesi.

### <a name="remarks"></a>Açıklamalar

Öğe, konum değiştikçe, sonuçları bir nesnenin örneklerini çöp toplayıcı yönetilen yığında izlemek yerel bir işaretçi kuramıyor. Doğru örneğine başvurmak bir işaretçi için çalışma zamanı konumlandırılmış yeni nesneye işaretçi güncelleştirmek gerekir.

Bir **interior_ptr** yerel bir işaretçi bir işlevselliğin temsil eder.  Bu nedenle, yerel bir işaretçiye atanabilir herhangi bir şey de atanabilir bir **interior_ptr**.  İç işaretçiye karşılaştırma ve işaretçi aritmetiğini dahil olmak üzere, yerel işaretçiler olarak aynı işlemleri kümesini gerçekleştirmek için izin verilir.

İç işaretçiye yalnızca yığında bildirilebilir.  İç işaretçiye bir sınıf üyesi olarak bildirilemez.

Yalnızca yığında iç işaretçiler mevcut olduğundan, iç işaretçiye adresinin alınmasına bir yönetilmeyen işaretçi verir.

**interior_ptr** örtük dönüştürmeleri vardır **bool**, veren kullanımını koşullu ifadeler için.

Atık toplanan yığında taşınamaz bir nesneye işaret eden bir işaretçiye bildirme hakkında daha fazla bilgi için bkz: [pin_ptr](pin-ptr-cpp-cli.md).

**interior_ptr** CLI ad alanındadır.  Bkz: [Platform, varsayılan ve cli ad alanları](platform-default-and-cli-namespaces-cpp-component-extensions.md) daha fazla bilgi için.

İç işaretçiler hakkında daha fazla bilgi için bkz.

- [Nasıl yapılır: İç işaretçiler ve yönetilen diziler bildirme ve kullanma (C + +/ CLI)](how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)

- [Nasıl yapılır: İnterior_ptr anahtar sözcüğü ile değer türleri bildirme (C + +/ CLI)](how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)

- [Nasıl yapılır: İç işaretçiler ve yerel işaretçilerle işlevleri tekrar yükleme (C + +/ CLI)](how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)

- [Nasıl yapılır: Const anahtar sözcüğü ile iç işaretçileri bildirme (C + +/ CLI)](how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, bildirme ve bir başvuru türü iç işaretçiye kullanma işlemi gösterilmektedir.

```cpp
// interior_ptr.cpp
// compile with: /clr
using namespace System;

ref class MyClass {
public:
   int data;
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   h_MyClass->data = 1;
   Console::WriteLine(h_MyClass->data);

   interior_ptr<int> p = &(h_MyClass->data);
   *p = 2;
   Console::WriteLine(h_MyClass->data);

   // alternatively
   interior_ptr<MyClass ^> p2 = &h_MyClass;
   (*p2)->data = 3;
   Console::WriteLine((*p2)->data);
}
```

```Output
1
2
3
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP için bileşen uzantıları](component-extensions-for-runtime-platforms.md)