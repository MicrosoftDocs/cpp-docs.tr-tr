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
ms.openlocfilehash: d0567c522e0e21f70b9ed8acfa428c3374fd09f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339546"
---
# `__declspec`

**Microsoft'a Özgü**

Depolama sınıfı bilgilerini belirtmek için genişletilmiş öznitelik söz dizimi, belirli bir **`__declspec`** türün örneğinin aşağıda listelenen Microsoft 'a özgü bir depolama sınıfı özniteliğiyle depolanabileceğini belirten anahtar sözcüğünü kullanır. Diğer depolama sınıfı değiştiricilerine örnekler **`static`** ve **`extern`** anahtar sözcüklerini içerir. Ancak bu anahtar sözcükler C ve C++ dillerinin ANSI belirtiminin bir parçasıdır ve genişletilmiş öznitelik söz dizimi kapsamında değildir. Genişletilmiş söz dizimi özniteliği Microsoft'a özel C ve C++ dilleri genişletmelerini basitleştirir ve standartlaştırır.

## <a name="grammar"></a>Dilbilgisi

*`decl-specifier`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`__declspec (`**  *`extended-decl-modifier-seq`*  **`)`**

*`extended-decl-modifier-seq`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`extended-decl-modifier`*<sub>et</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*`extended-decl-modifier`* *`extended-decl-modifier-seq`*

*`extended-decl-modifier`*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`align(`***sayı***`)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`allocate("`***segname***`")`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`allocator`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`appdomain`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`code_seg("`***segname***`")`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`deprecated`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`dllimport`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`dllexport`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`jitintrinsic`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`naked`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`noalias`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`noinline`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`noreturn`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`nothrow`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`novtable`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`process`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`property(`**{ **`get=`** _Get-Func-Name_ &#124; **`,put=`** _PUT-Func-Name_ }**`)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`restrict`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`safebuffers`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`selectany`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`spectre(nomitigation)`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`thread`**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**`uuid("`***Comobjectguid***`")`**

Beyaz boşluk, bildirim değiştirici sırasını ayırır. Örnekler sonraki bölümlerde gösterilir.

Genişletilmiş öznitelik dilbilgisi, Microsoft 'a özgü bu depolama sınıfı özniteliklerini destekler: [`align`](../cpp/align-cpp.md) , [`allocate`](../cpp/allocate.md) , [`allocator`](../cpp/allocator.md) , [`appdomain`](../cpp/appdomain.md) , [`code_seg`](../cpp/code-seg-declspec.md) , [`deprecated`](../cpp/deprecated-cpp.md) , [`dllexport`](../cpp/dllexport-dllimport.md) , [`dllimport`](../cpp/dllexport-dllimport.md) , [`jitintrinsic`](../cpp/jitintrinsic.md) , [`naked`](../cpp/naked-cpp.md) , [`noalias`](../cpp/noalias.md) , [`noinline`](../cpp/noinline.md) , [`noreturn`](../cpp/noreturn.md) , [`nothrow`](../cpp/nothrow-cpp.md) , [`novtable`](../cpp/novtable.md) , [`process`](../cpp/process.md) , [`restrict`](../cpp/restrict.md) , [`safebuffers`](../cpp/safebuffers.md) , [`selectany`](../cpp/selectany.md) [`spectre`](../cpp/spectre.md) [`thread`](../cpp/thread.md) ,,,,,, ve. Ayrıca, bu COM nesnesi özniteliklerini de destekler: [`property`](../cpp/property-cpp.md) ve [`uuid`](../cpp/uuid-cpp.md) .

,,,, **`code_seg`** **`dllexport`** **`dllimport`** **`naked`** **`noalias`** , **`nothrow`** ,,,, **`property`** **`restrict`** **`selectany`** **`thread`** Ve **`uuid`** depolama sınıfı öznitelikleri yalnızca uygulandıkları nesne veya işlev bildiriminin özellikleridir. **`thread`** Özniteliği yalnızca verileri ve nesneleri etkiler. **`naked`** Ve **`spectre`** öznitelikleri yalnızca işlevleri etkiler. **`dllimport`** Ve **`dllexport`** öznitelikleri işlevleri, verileri ve nesneleri etkiler. **`property`**, **`selectany`** Ve **`uuid`** öznitelikleri com nesnelerini etkiler.

Önceki sürümlerle uyumluluk için, **`_declspec`** **`__declspec`** [/za \( Disable dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirlenmediği için bir eş anlamlı.

**`__declspec`** Anahtar sözcükler basit bir bildirimin başlangıcına yerleştirilmelidir. Derleyici, uyarı olmadan, **`__declspec`** * veya & sonra gelen anahtar kelimeleri ve bir bildirimde değişken tanımlayıcısının önüne konur.

**`__declspec`** Kullanıcı tanımlı tür bildiriminin başlangıcında belirtilen öznitelik, bu tür değişkeni için geçerlidir. Örneğin:

```cpp
__declspec(dllimport) class X {} varX;
```

Bu durumda, özniteliği için geçerlidir `varX` . **`__declspec`** Veya anahtar sözcüğünden sonra yerleştirilmiş bir öznitelik, **`class`** **`struct`** Kullanıcı tanımlı tür için geçerlidir. Örneğin:

```cpp
class __declspec(dllimport) X {};
```

Bu durumda, özniteliği için geçerlidir `X` .

Basit bildirimlerin özniteliğini kullanmaya yönelik genel kılavuz **`__declspec`** aşağıdaki gibidir:

*decl-belirleyicisi-Seq* *init-declarator-list*;

*Decl-belirleyicisi-Seq* , diğer şeyleri, bir temel türü (örn., **`int`** **`float`** bir **`typedef`** veya bir sınıf adı), bir depolama sınıfı (örn. **`static`** **`extern`** ) veya **`__declspec`** uzantıyı içermelidir. *İnit-declarator-list* , diğer şeyleri, bildirimlerin işaretçi parçasını içermelidir. Örneğin:

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

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[C genişletilmiş Storage-Class öznitelikleri](../c-language/c-extended-storage-class-attributes.md)
