---
title: __declspec | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b434ca991ef05bb90c3cbdc659cf8adc3381aa0
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752923"
---
# <a name="declspec"></a>__declspec

**Microsoft'a özgü**

Depolama sınıfı bilgilerini kullanan belirtmek için genişletilmiş öznitelik söz dizimi **__declspec** anahtar sözcük belirli bir türün bir örneği aşağıda listelenen Microsoft'a özgü depolama sınıfı özniteliğiyle depolanması gerektiğini belirtir. Diğer depolama sınıfı değiştiricilere ait örnekler **statik** ve **extern** anahtar sözcükleri. Ancak bu anahtar sözcükler C ve C++ dillerinin ANSI belirtiminin bir parçasıdır ve genişletilmiş öznitelik söz dizimi kapsamında değildir. Genişletilmiş söz dizimi özniteliği Microsoft'a özel C ve C++ dilleri genişletmelerini basitleştirir ve standartlaştırır.

## <a name="grammar"></a>Dilbilgisi

*Decl-specifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (***genişletilmiş-decl-değiştirici-seq***)** 

*extended-decl-modifier-seq*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-değiştirici*<sub>iyileştirilmiş</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş-decl-değiştirici* *genişletilmiş-decl-değiştirici-seq*

*Genişletilmiş-decl-değiştirici*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Hizalama (** *#* **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ayırın ("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**AppDomain**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg ("** *segname* **")**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kullanım dışı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**naked**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**İşlem**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**özellik (** { **alma =**_get_func_name_ &#124; **, put =**_put_func_name_ } **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**kısıtlama**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**spectre(nomitigation)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**iş parçacığı**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uuid ("** *ComObjectGUID* **")**

Beyaz boşluk, bildirim değiştirici sırasını ayırır. Örnekler sonraki bölümlerde gösterilir.

Genişletilmiş öznitelik dilbilgisi bu Microsoft'a özgü depolama sınıfı öznitelikler destekler: [hizalama](../cpp/align-cpp.md), [tahsis](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [kullanım dışı](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md) , [işlem](../cpp/process.md), [kısıtlama](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), [spectre](../cpp/spectre.md), ve [iş parçacığı](../cpp/thread.md). Ayrıca bu COM nesnesi özniteliklerini de destekler: [özelliği](../cpp/property-cpp.md) ve [UUID](../cpp/uuid-cpp.md).

**Code_seg**, **dllexport**, **dllimport**, **naked**, **noalias**, **nothrow** , **özelliği**, **kısıtlama**, **selectany**, **iş parçacığı**, ve **UUID**depolama sınıfı öznitelikleri yalnızca nesne veya işlev için bunlar uygulandığı bildirimin özellikleridir. **İş parçacığı** özniteliği yalnızca nesneleri ve verileri etkiler. **Naked** ve **spectre** öznitelikleri yalnızca işlevleri etkiler. **Dllimport** ve **dllexport** öznitelikleri işlevleri, verileri ve nesneleri etkiler. **Özelliği**, **selectany**, ve **UUID** öznitelikleri COM nesnelerini etkiler.

**__Declspec** anahtar sözcükleri basit bir bildirimin başlangıcına yerleştirilmelidir. Uyarı derleyicinin yoksaydığı **__declspec** anahtar sözcükleri yerleştirilen sonra * veya & ve bir bildirimde değişken tanımlayıcının önündeki.

A **__declspec** kullanıcı tanımlı tür bildiriminin başında belirtilen özniteliği bu türün değişkenlerine uygulanır. Örneğin:

```cpp
__declspec(dllimport) class X {} varX;
```

Öznitelik uygulandığı bu durumda, `varX`. A **__declspec** özniteliği yerleştirilen sonra **sınıfı** veya **yapı** anahtar sözcüğü kullanıcı tanımlı türe uygulanır. Örneğin:

```cpp
class __declspec(dllimport) X {};
```

Öznitelik uygulandığı bu durumda, `X`.

Kullanmaya yönelik genel yönerge **__declspec** basit bildirimler için öznitelik şu şekildedir:

*Decl-specifier-seq* *init-declarator-list*;

*Decl-specifier-seq* , diğerlerinin yanı sıra bir taban türü içermelidir (örneğin **int**, **float**, **typedef**, veya bir sınıf adı), depolama sınıfı (örn **statik**, **extern**), veya **__declspec** uzantısı. *İnit-declarator-list* , diğerlerinin yanında bildirimlerin işaretçi bölümünü de içermelidir. Örneğin:

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)  
 [C Genişletilmiş Depolama Sınıfı Öznitelikler](../c-language/c-extended-storage-class-attributes.md)  