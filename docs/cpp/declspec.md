---
title: __declspec
ms.date: 03/21/2019
f1_keywords:
- __declspec_cpp
- __declspec
- _declspec
helpviewer_keywords:
- __declspec keyword [C++]
ms.openlocfilehash: e0c99ea9379aa6e29096250e8bd36ce3d4f183e8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180231"
---
# <a name="__declspec"></a>__declspec

**Microsoft 'a özgü**

Depolama sınıfı bilgilerini belirtmek için genişletilmiş öznitelik sözdizimi, belirli bir türün örneğinin aşağıda listelenen Microsoft 'a özgü bir depolama sınıfı özniteliğiyle depolanabileceğini belirten **__declspec** anahtar sözcüğünü kullanır. Diğer depolama sınıfı değiştiricilerine örnekler **statik** ve **extern** anahtar sözcüklerini içerir. Ancak bu anahtar sözcükler C ve C++ dillerinin ANSI belirtiminin bir parçasıdır ve genişletilmiş öznitelik söz dizimi kapsamında değildir. Genişletilmiş söz dizimi özniteliği Microsoft'a özel C ve C++ dilleri genişletmelerini basitleştirir ve standartlaştırır.

## <a name="grammar"></a>Dilbilgisi

*decl-belirleyicisi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__declspec (** *Genişletilmiş-decl-değiştirici-seq* **)**

*Genişletilmiş-decl-Modifier-Seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-Modifier*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-Modifier* *Genişletilmiş-decl-Modifier-Seq*

*Extended-decl-değiştirici*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Hizalama (** *#* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ayır ("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ayırıcısı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**AppDomain**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg ("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;**kullanım dışı** &nbsp;<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**jiç**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noline**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**işlem**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Özelliği (** { **Get =** _get_func_name_ &#124; **, put =** _put_func_name_ } **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kısıtla**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Spectre (noazaltma)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**iş parçacığı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**UUID ("** *comobjectguid* **")**

Beyaz boşluk, bildirim değiştirici sırasını ayırır. Örnekler sonraki bölümlerde gösterilir.

Genişletilmiş öznitelik dilbilgisi, Microsoft 'a özgü bu depolama sınıfı özniteliklerini destekler: [align](../cpp/align-cpp.md), [allocate](../cpp/allocate.md), [ayırıcı](../cpp/allocator.md), [AppDomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [kullanım dışı](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jic](../cpp/jitintrinsic.md), [Naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md), [işlem](../cpp/process.md), [kısıtlama](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), [ Spectre](../cpp/spectre.md)ve [iş parçacığı](../cpp/thread.md). Ayrıca, bu COM nesnesi özniteliklerini de destekler: [özellik](../cpp/property-cpp.md) ve [UUID](../cpp/uuid-cpp.md).

**Code_seg**, **dllexport**, **dllimport**, **Naked**, **noalias**, **nothrow**, **Property**, **kısıtlamalı**, **selectany**, **thread**ve **UUID** depolama sınıfı öznitelikleri yalnızca uygulandıkları nesne veya işlev bildiriminin özellikleridir. **Thread** özniteliği yalnızca verileri ve nesneleri etkiler. **Naked** ve **Spectre** öznitelikleri yalnızca işlevleri etkiler. **Dllimport** ve **dllexport** öznitelikleri işlevleri, verileri ve nesneleri etkiler. **Özelliği**, **selectany**ve **UUID** öznitelikleri com nesnelerini etkiler.

Önceki sürümlerle uyumluluk için, [/za \(dil uzantılarını devre dışı bırak](../build/reference/za-ze-disable-language-extensions.md) derleyici seçeneği belirtildiğinde, **_declspec** **__declspec** için bir eş anlamlı.

**__Declspec** anahtar sözcükleri basit bir bildirimin başlangıcına yerleştirilmelidir. Derleyici, uyarı olmadan, * veya & sonra ve bir bildirimde değişken tanımlayıcısının önüne yerleştirilmiş tüm **__declspec** anahtar sözcüklerini yok sayar.

Kullanıcı tanımlı tür bildiriminin başlangıcında belirtilen bir **__declspec** özniteliği, bu tür değişkeni için geçerlidir. Örneğin:

```cpp
__declspec(dllimport) class X {} varX;
```

Bu durumda, öznitelik `varX`için geçerlidir. **Sınıf** veya **Yapı** anahtar sözcüğünden sonra konulan **__declspec** özniteliği Kullanıcı tanımlı tür için geçerlidir. Örneğin:

```cpp
class __declspec(dllimport) X {};
```

Bu durumda, öznitelik `X`için geçerlidir.

Basit bildirimlerin **__declspec** özniteliğini kullanmanın genel Kılavuzu aşağıdaki gibidir:

*decl-belirleyicisi-Seq* *init-declarator-list*;

*Decl-belirleyicisi-Seq* , diğer şeyleri (örneğin, **int**, **float**, bir **typedef**veya bir sınıf adı), bir depolama sınıfı (örn. **statik**, **extern**) veya **__declspec** uzantısını içermelidir. *İnit-declarator-list* , diğer şeyleri, bildirimlerin işaretçi parçasını içermelidir. Örneğin:

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

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[C Genişletilmiş Depolama Sınıfı Öznitelikler](../c-language/c-extended-storage-class-attributes.md)
