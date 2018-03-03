---
title: __declspec | Microsoft Docs
ms.custom: 
ms.date: 1/23/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51a08092160ecb288decae343713e5a4f6e507b1
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="declspec"></a>__declspec

**Microsoft Specific**

Depolama sınıfı bilgi kullanır belirtmek için genişletilmiş öznitelik sözdizimi **__declspec** anahtar sözcüğü belirli bir türün bir örneği aşağıda listelenen Microsoft'a özgü depolama sınıfı öznitelik ile depolanması için olduğunu belirtir. Diğer depolama sınıfı değiştiricileri örneklerindendir **statik** ve **extern** anahtar sözcükler. Ancak bu anahtar sözcükler C ve C++ dillerinin ANSI belirtiminin bir parçasıdır ve genişletilmiş öznitelik söz dizimi kapsamında değildir. Genişletilmiş söz dizimi özniteliği Microsoft'a özel C ve C++ dilleri genişletmelerini basitleştirir ve standartlaştırır.

## <a name="grammar"></a>Dilbilgisi

*Decl belirleyici*:  
&nbsp;&nbsp;&nbsp;&nbsp;**__declspec (***genişletilmiş-decl-değiştirici-seq***)** 

*extended-decl-modifier-seq*:  
&nbsp;&nbsp;&nbsp;&nbsp;*extended-decl-modifier*<sub>opt</sub>  
&nbsp;&nbsp;&nbsp;&nbsp;*Genişletilmiş decl-değiştirici* *genişletilmiş-decl-değiştirici-seq*

*extended-decl-modifier*:  
&nbsp;&nbsp;&nbsp;&nbsp;**Hizalama (**  *#*  **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**ayırma ("** *segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**AppDomain**  
&nbsp;&nbsp;&nbsp;&nbsp;**code_seg("** *segname* **")**  
&nbsp;&nbsp;&nbsp;&nbsp;**kullanım dışı**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllimport**  
&nbsp;&nbsp;&nbsp;&nbsp;**dllexport**  
&nbsp;&nbsp;&nbsp;&nbsp;**jitintrinsic**  
&nbsp;&nbsp;&nbsp;&nbsp;**naked**  
&nbsp;&nbsp;&nbsp;&nbsp;**noalias**  
&nbsp;&nbsp;&nbsp;&nbsp;**noinline**  
&nbsp;&nbsp;&nbsp;&nbsp;**noreturn**  
&nbsp;&nbsp;&nbsp;&nbsp;**nothrow**  
&nbsp;&nbsp;&nbsp;&nbsp;**novtable**  
&nbsp;&nbsp;&nbsp;&nbsp;**işlem**  
&nbsp;&nbsp;&nbsp;&nbsp;**property(** { **get=**_get_func_name_ &#124; **,put=**_put_func_name_ } **)**  
&nbsp;&nbsp;&nbsp;&nbsp;**restrict**  
&nbsp;&nbsp;&nbsp;&nbsp;**safebuffers**  
&nbsp;&nbsp;&nbsp;&nbsp;**selectany**  
&nbsp;&nbsp;&nbsp;&nbsp;**spectre(nomitigation)**  
&nbsp;&nbsp;&nbsp;&nbsp;**iş parçacığı**  
&nbsp;&nbsp;&nbsp;&nbsp;**uuid("** *ComObjectGUID* **")**  

Beyaz boşluk, bildirim değiştirici sırasını ayırır. Örnekler sonraki bölümlerde gösterilir.

Genişletilmiş öznitelik dilbilgisi bu Microsoft'a özgü depolama sınıfı öznitelikler destekler: [Hizala](../cpp/align-cpp.md), [tahsis](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [kullanım dışı](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md) , [işlem](../cpp/process.md), [kısıtlamak](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), [spectre](../cpp/spectre.md), ve [iş parçacığı](../cpp/thread.md). Bu COM Nesne öznitelikleri de destekler: [özelliği](../cpp/property-cpp.md) ve [UUID](../cpp/uuid-cpp.md).

**Code_seg**, **dllexport**, **dllimport**, **naked**, **noalias**, **nothrow** , **özelliği**, **kısıtlamak**, **selectany**, **iş parçacığı**, ve **UUID**depolama sınıfı öznitelikler nesne ya da bunlar uygulanan işlev bildirimi, yalnızca özelliklerdir. **İş parçacığı** özniteliği yalnızca nesneleri ve veri etkiler. **Naked** ve **spectre** öznitelikleri işlevleri yalnızca etkiler. **Dllimport** ve **dllexport** öznitelikleri İşlevler, veri ve nesneleri etkiler. **Özelliği**, **selectany**, ve **UUID** öznitelikleri COM nesneleri etkiler.

**__Declspec** anahtar sözcükleri basit bir bildirimi başında yerleştirilmelidir. Her uyarı vermeden derleyici yoksayar **__declspec** anahtar sözcükleri yerleştirilen sonra * veya & ve bir bildirimde değişken tanımlayıcısı.

A **__declspec** bir kullanıcı tanımlı tür bildirimi başına içinde belirtilen öznitelik türü değişkenine uygular. Örneğin:

```cpp
__declspec(dllimport) class X {} varX;
```

Bu durumda, öznitelik uygulandığı öğe `varX`. A **__declspec** özniteliği yerleştirilen sonra **sınıfı** veya **yapısı** anahtar sözcüğü kullanıcı tanımlı tür için geçerlidir. Örneğin:

```cpp
class __declspec(dllimport) X {};
```

Bu durumda, öznitelik uygulandığı öğe `X`.

Kullanmak için genel kural **__declspec** basit bildirimleri özniteliği aşağıdaki gibidir:

*decl-specifier-seq* *init-declarator-list*;

*Decl belirleyici seq* , bunun yanı sıra, bir taban türü içermelidir (örneğin **int**, **float**, **typedef**, ya da bir sınıf adı), depolama sınıfı (örneğin **statik**, **extern**), veya **__declspec** uzantısı. *İnit bildirimcisi listesi* , bunun yanı sıra, bildirimler işaretçi parçası içermelidir. Örneğin:

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

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)  
[C Genişletilmiş Depolama Sınıfı Öznitelikler](../c-language/c-extended-storage-class-attributes.md)  
