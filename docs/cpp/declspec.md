---
title: __declspec | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __declspec_cpp
dev_langs: C++
helpviewer_keywords: __declspec keyword [C++]
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0351b5ba8469918dfe52462485ebf36255db56fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="declspec"></a>__declspec
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Depolama sınıfı bilgi kullanır belirtmek için genişletilmiş öznitelik sözdizimi `__declspec` anahtar sözcüğü belirli bir türün bir örneği aşağıda listelenen Microsoft'a özgü depolama sınıfı öznitelik ile depolanması için olduğunu belirtir. Diğer depolama sınıfı değiştiricileri örneklerindendir `static` ve `extern` anahtar sözcükler. Ancak bu anahtar sözcükler C ve C++ dillerinin ANSI belirtiminin bir parçasıdır ve genişletilmiş öznitelik söz dizimi kapsamında değildir. Genişletilmiş söz dizimi özniteliği Microsoft'a özel C ve C++ dilleri genişletmelerini basitleştirir ve standartlaştırır.  
  
## <a name="grammar"></a>Dilbilgisi  
 *Decl belirleyici*:  
 `__declspec (`  *Genişletilmiş-decl-değiştirici-seq*  `)`  
  
 *Genişletilmiş-decl-değiştirici-seq*:  
 *Genişletilmiş decl-değiştirici*iptal et  
  
 *Genişletilmiş decl-değiştirici genişletilmiş-decl-değiştirici-seq*  
  
 *Genişletilmiş decl-değiştirici*:  
 `align(` *#* `)`  
  
 `allocate("`*segname*`")`  
  
 `appdomain`  
  
 `code_seg("`*segname*`")`  
  
 `deprecated`  
  
 `dllimport`  
  
 `dllexport`  
  
 `jitintrinsic`  
  
 `naked`  
  
 `noalias`  
  
 `noinline`  
  
 `noreturn`  
  
 `nothrow`  
  
 `novtable`  
  
 `process`  
  
 `property(`{`get=`*get_func_name*&#124;`,put=` *put_func_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("`*ComObjectGUID*`")`  
  
 Beyaz boşluk, bildirim değiştirici sırasını ayırır. Örnekler sonraki bölümlerde gösterilir.  
  
 Genişletilmiş öznitelik dilbilgisi bu Microsoft'a özgü depolama sınıfı öznitelikler destekler: [Hizala](../cpp/align-cpp.md), [tahsis](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [kullanım dışı](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md) , [işlem](../cpp/process.md), [kısıtlamak](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), ve [iş parçacığı](../cpp/thread.md). Bu COM Nesne öznitelikleri de destekler: [özelliği](../cpp/property-cpp.md) ve [UUID](../cpp/uuid-cpp.md).  
  
 `code_seg`, `dllexport`, `dllimport`, `naked`, `noalias`, `nothrow`, `property`, `restrict`, `selectany`, `thread`, Ve `uuid` özelliklerdir depolama sınıfı öznitelikler yalnızca bildirimi nesnesinin ya da uygulanan işlev. `thread` Özniteliği yalnızca nesneleri ve veri etkiler. `naked` Özniteliği yalnızca işlevleri etkiler. `dllimport` Ve `dllexport` öznitelikleri İşlevler, veri ve nesneleri etkiler. `property`, `selectany`, Ve `uuid` öznitelikleri COM nesneleri etkiler.  
  
 `__declspec` Anahtar sözcükleri basit bir bildirimi başında yerleştirilmelidir. Her uyarı vermeden derleyici yoksayar `__declspec` anahtar sözcükleri yerleştirilen sonra * veya & ve bir bildirimde değişken tanımlayıcısı.  
  
 A `__declspec` bir kullanıcı tanımlı tür bildirimi başına içinde belirtilen öznitelik türü değişkenine uygular. Örneğin:  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 Bu durumda, öznitelik uygulandığı öğe `varX`. A `__declspec` özniteliği yerleştirilen sonra `class` veya `struct` anahtar sözcüğü kullanıcı tanımlı tür için geçerlidir. Örneğin:  
  
```  
class __declspec(dllimport) X {};  
```  
  
 Bu durumda, öznitelik uygulandığı öğe `X`.  
  
 Kullanmak için genel kural `__declspec` basit bildirimleri özniteliği aşağıdaki gibidir:  
  
```  
  
decl-specifier-seq  
declarator-list;  
```  
  
 *Decl belirleyici seq* , bunun yanı sıra, bir taban türü içermelidir (örneğin `int`, `float`, `typedef`, ya da bir sınıf adı), depolama sınıfı (örneğin `static`, `extern`), veya `__declspec`uzantısı. *İnit bildirimcisi listesi* , bunun yanı sıra, bildirimler işaretçi parçası içermelidir. Örneğin:  
  
```  
__declspec(selectany) int * pi1 = 0;   //OK, selectany & int both part of decl-specifier  
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier  
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator  
```  
  
 Aşağıdaki kod bir tamsayı iş parçacığı yerel değişkeni bildirir ve bunu bir değer ile başlatır:  
  
```  
// Example of the __declspec keyword  
__declspec( thread ) int tls_i = 1;  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [C Genişletilmiş Depolama Sınıfı Öznitelikler](../c-language/c-extended-storage-class-attributes.md)