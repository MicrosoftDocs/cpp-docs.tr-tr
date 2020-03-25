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
ms.openlocfilehash: 264ac0a56996b0dcbeeb64246623eca1a3fc73ff
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172158"
---
# <a name="interior_ptr-ccli"></a>interior_ptr (C++/CLI)

*İç işaretçi* bir başvuru türünün içinde bir işaretçi bildirir ancak nesnenin kendisi için değildir. İç işaretçi bir başvuru tanıtıcısı, değer türü, paketlenmiş tür tanıtıcısı, yönetilen bir türün üyesi veya yönetilen bir dizinin bir öğesi ile işaret edebilir.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliği için tüm çalışma zamanları için uygulanan bir açıklama yoktur.)

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

(Bu dil özelliği için yalnızca Windows Çalışma Zamanı uygulanan bir açıklama yoktur.)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

Aşağıdaki sözdizimi örneği iç işaretçiyi gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
cli::interior_ptr<cv_qualifier type> var = &initializer;
```

### <a name="parameters"></a>Parametreler

*cv_qualifier*<br/>
**const** veya **volatile** niteleyicileri.

*type*<br/>
*Başlatıcı*türü.

*var*<br/>
**İnterior_ptr** değişkeninin adı.

*izer*<br/>
Bir başvuru türünün üyesi, yönetilen bir dizinin öğesi ya da yerel bir işaretçiye atayabileceğiniz başka herhangi bir nesne.

### <a name="remarks"></a>Açıklamalar

Yerel bir işaretçi, yönetilen yığında konum değişiklikleri olarak bir nesneyi takip edemeyebilir, bu da nesnenin çöp toplayıcı hareketli örneklerinin sonucunu elde etmez. Bir işaretçinin örneğe doğru bir şekilde başvurması için, çalışma zamanının işaretçiyi yeni konumlandırılmış nesneye güncelleştirmesi gerekir.

**İnterior_ptr** , yerel işaretçinin işlevselliğinin bir üst kümesini temsil eder.  Bu nedenle, yerel bir işaretçiye atanabilecek her türlü şey bir **interior_ptr**da atanabilir.  İç işaretçiye karşılaştırma ve işaretçi aritmetiği dahil olmak üzere yerel işaretçilerle aynı işlem kümesi gerçekleştirmesine izin verilir.

İç işaretçi yalnızca yığında bildirilebilecek.  İç işaretçi bir sınıfın üyesi olarak bildirilemez.

İç işaretçiler yalnızca yığında olduğundan, iç işaretçinin adresini almak yönetilmeyen bir işaretçi verir.

**interior_ptr** , **bool**'a örtük dönüştürmeye sahiptir ve bu, Koşullu deyimlerde kullanılmasına olanak tanır.

Atık toplanmış yığında taşınamayan bir nesneye işaret eden iç işaretçiyi bildirme hakkında daha fazla bilgi için bkz. [pin_ptr](pin-ptr-cpp-cli.md).

**interior_ptr** CLI ad alanıdır.  Daha fazla bilgi için bkz. [Platform, varsayılan ve CLI ad alanları](platform-default-and-cli-namespaces-cpp-component-extensions.md) .

İç işaretçiler hakkında daha fazla bilgi için bkz.

- [Nasıl yapılır: İç İşaretçiler ve Yönetilen Diziler Bildirme ve Kullanma (C++/CLI)](how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)

- [Nasıl yapılır: interior_ptr Anahtar Sözcüğü ile Değer Türleri Bildirme (C++/CLI)](how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)

- [Nasıl yapılır: İç İşaretçiler ve Yerel İşaretçilerle İşlevleri Tekrar Yükleme (C++/CLI)](how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)

- [Nasıl yapılır: const Anahtar Sözcüğü ile İç İşaretçileri Bildirme (C++/CLI)](how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki örnek, bir iç işaretçinin bir başvuru türü içinde nasıl bildirilemeyeceğini ve kullanılacağını göstermektedir.

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

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
