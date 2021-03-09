---
description: 'Hakkında daha fazla bilgi edinin: `__declspec`'
title: __declspec
ms.date: 03/21/2019
f1_keywords:
- __declspec_cpp
- __declspec
- _declspec
helpviewer_keywords:
- __declspec keyword [C++]
ms.openlocfilehash: 1a8644bc05319332967ffd7934e6799408c3d36d
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102465534"
---
# `__declspec`

**Microsoft'a Özgü**

Depolama sınıfı bilgilerini belirtmek için genişletilmiş öznitelik söz dizimi, belirli bir **`__declspec`** türün örneğinin aşağıda listelenen Microsoft 'a özgü bir depolama sınıfı özniteliğiyle depolanabileceğini belirten anahtar sözcüğünü kullanır. Diğer depolama sınıfı değiştiricilerine örnekler **`static`** ve **`extern`** anahtar sözcüklerini içerir. Ancak bu anahtar sözcükler C ve C++ dillerinin ANSI belirtiminin bir parçasıdır ve genişletilmiş öznitelik söz dizimi kapsamında değildir. Genişletilmiş söz dizimi özniteliği Microsoft'a özel C ve C++ dilleri genişletmelerini basitleştirir ve standartlaştırır.

## <a name="grammar"></a>Dilbilgisi

*`decl-specifier`*:\
&emsp;**`__declspec (`**  *`extended-decl-modifier-seq`*  **`)`**

*`extended-decl-modifier-seq`*:\
&emsp;*`extended-decl-modifier`*<sub>et</sub>\
&emsp;*`extended-decl-modifier`* *`extended-decl-modifier-seq`*

*`extended-decl-modifier`*:\
&emsp;**`align(`***sayı***`)`**\
&emsp;**`allocate("`***segname***`")`**\
&emsp;**`allocator`**\
&emsp;**`appdomain`**\
&emsp;**`code_seg("`***segname***`")`**\
&emsp;**`deprecated`**\
&emsp;**`dllimport`**\
&emsp;**`dllexport`**\
&emsp;**`jitintrinsic`**\
&emsp;**`naked`**\
&emsp;**`noalias`**\
&emsp;**`noinline`**\
&emsp;**`noreturn`**\
&emsp;**`nothrow`**\
&emsp;**`novtable`**\
&emsp;**`no_sanitize_address`**\
&emsp;**`process`**\
&emsp;**`property(`**{ **`get=`** _Get-Func-Name_ &#124; **`,put=`** _PUT-Func-Name_ }**`)`**\
&emsp;**`restrict`**\
&emsp;**`safebuffers`**\
&emsp;**`selectany`**\
&emsp;**`spectre(nomitigation)`**\
&emsp;**`thread`**\
&emsp;**`uuid("`***Comobjectguid***`")`**

Beyaz boşluk, bildirim değiştirici sırasını ayırır. Örnekler sonraki bölümlerde gösterilir.

Genişletilmiş öznitelik dilbilgisi, Microsoft 'a özgü bu depolama sınıfı özniteliklerini destekler: [`align`](../cpp/align-cpp.md) , [`allocate`](../cpp/allocate.md) , [`allocator`](../cpp/allocator.md) , [`appdomain`](../cpp/appdomain.md) , [`code_seg`](../cpp/code-seg-declspec.md) , [`deprecated`](../cpp/deprecated-cpp.md) , [`dllexport`](../cpp/dllexport-dllimport.md) , [`dllimport`](../cpp/dllexport-dllimport.md) , [`jitintrinsic`](../cpp/jitintrinsic.md) , [`naked`](../cpp/naked-cpp.md) , [`noalias`](../cpp/noalias.md) , [`noinline`](../cpp/noinline.md) , [`noreturn`](../cpp/noreturn.md) , [`nothrow`](../cpp/nothrow-cpp.md) , [`novtable`](../cpp/novtable.md) , [`no_sanitize_address`](../cpp/no-sanitize-address.md) , [`process`](../cpp/process.md) , [`restrict`](../cpp/restrict.md) , [`safebuffers`](../cpp/safebuffers.md) [`selectany`](../cpp/selectany.md) [`spectre`](../cpp/spectre.md) [`thread`](../cpp/thread.md) ,,,,,,, ve. Ayrıca, bu COM nesnesi özniteliklerini de destekler: [`property`](../cpp/property-cpp.md) ve [`uuid`](../cpp/uuid-cpp.md) .

,,,,,,,,,,,,,,, **`code_seg`** **`dllexport`** **`dllimport`** **`naked`** **`noalias`** **`nothrow`** **`no_sanitize_address`** **`property`** **`restrict`** **`selectany`** **`thread`** Ve **`uuid`** depolama sınıfı öznitelikleri yalnızca uygulandıkları nesne veya işlev bildirimi özelliklerdir. **`thread`** Özniteliği yalnızca verileri ve nesneleri etkiler. **`naked`** Ve **`spectre`** öznitelikleri yalnızca işlevleri etkiler. **`dllimport`** Ve **`dllexport`** öznitelikleri işlevleri, verileri ve nesneleri etkiler. **`property`**, **`selectany`** Ve **`uuid`** öznitelikleri com nesnelerini etkiler.

Önceki sürümlerle uyumluluk için, **`_declspec`** **`__declspec`** [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirlenmediği için bir eş anlamlı.

**`__declspec`** Anahtar sözcükler basit bir bildirimin başlangıcına yerleştirilmelidir. Derleyici, uyarı olmadan, **`__declspec`** * veya & sonra gelen anahtar kelimeleri ve bir bildirimde değişken tanımlayıcısının önüne konur.

**`__declspec`** Kullanıcı tanımlı tür bildiriminin başlangıcında belirtilen öznitelik, bu tür değişkeni için geçerlidir. Örnek:

```cpp
__declspec(dllimport) class X {} varX;
```

Bu durumda, özniteliği için geçerlidir `varX` . **`__declspec`** Veya anahtar sözcüğünden sonra yerleştirilmiş bir öznitelik, **`class`** **`struct`** Kullanıcı tanımlı tür için geçerlidir. Örnek:

```cpp
class __declspec(dllimport) X {};
```

Bu durumda, özniteliği için geçerlidir `X` .

Basit bildirimlerin özniteliğini kullanmaya yönelik genel kılavuz **`__declspec`** aşağıdaki gibidir:

*decl-belirleyicisi-Seq* *init-declarator-list*;

*Decl-belirleyicisi-Seq* , diğer şeyleri, bir temel türü (örn., **`int`** **`float`** bir **`typedef`** veya bir sınıf adı), bir depolama sınıfı (örn. **`static`** **`extern`** ) veya **`__declspec`** uzantıyı içermelidir. *İnit-declarator-list* , diğer şeyleri, bildirimlerin işaretçi parçasını içermelidir. Örnek:

```cpp
__declspec(selectany) int * pi1 = 0;   //Recommended, selectany & int both part of decl-specifier
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator
```

Aşağıdaki kod bir tamsayı iş parçacığı yerel değişkeni bildirir ve bunu bir değer ile başlatır:

```cpp
// Example of the __declspec keyword
__declspec( thread ) int tls_i = 1;
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Lerimi](../cpp/keywords-cpp.md)\
[C genişletilmiş Storage-Class öznitelikleri](../c-language/c-extended-storage-class-attributes.md)
