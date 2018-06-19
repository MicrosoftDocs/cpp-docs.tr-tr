---
title: Pragma yönergeleri ve __Pragma anahtar sözcüğü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#pragma'
dev_langs:
- C++
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b20a476e1701f58782b97f986ee6c3d4b310b566
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846239"
---
# <a name="pragma-directives-and-the-pragma-keyword"></a>Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü
Pragma yönergeleri makine veya işletim özgü derleyicisi özelliklerini belirtin. `__pragma` Microsoft derleyici özel anahtar sözcüğü makrosu tanımları içindeki kod pragma yönergeleri için sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      #pragma token-string  
__pragma(token-string)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 C ve C++ her uygulama bazı özellikler, konak makine ya da işletim sistemi benzersiz destekler. Örneğin, bazı programlar kesin bir denetim verileri nerede yerleştirme bellek alanları üzerinden veya İşlevler alma parametrelerini belirli şeklini denetlemek için çalışma gerekir. `#pragma` Yönergeleri C ve C++ dilleri ile genel uyumluluk korurken makine ve işletim sistemine özgü özellikleri sunmak her derleyici için bir yol sunar.  
  
 Pragmaları makine veya işletim sistemi-tanımı tarafından özgüdür ve her derleyici için genellikle farklıdır. Pragmaları koşullu deyimlerinde yeni önişlemci işlevselliği sağlamak için veya uygulama tarafından tanımlanan bilgileri derleyici sağlamak için kullanılabilir.  
  
 `token-string` Belirli derleyici yönerge ve bağımsız değişkenler, veren karakterleri varsa dizisidir. Sayı işareti (**#**) ilk boşluk olmayan karakter pragma içeren satırı; boşluk karakterleri sayı işareti ve "pragma" word ayırabilirsiniz. Aşağıdaki `#pragma`, Çevirici belirteçleri ön işleme olarak ayrıştıramıyor herhangi bir metin yazın. Bağımsız değişkeni `#pragma` makrosu genişletme tabi değil.  
  
 Derleyici tarafından tanınmayan bir pragma bulursa, bir uyarı verir ve derleme devam eder.  
  
 Microsoft C ve C++ Derleyicileri aşağıdaki pragmaları algılar:  
  
||||  
|-|-|-|  
|[alloc_text](../preprocessor/alloc-text.md)|[auto_inline](../preprocessor/auto-inline.md)|[bss_seg](../preprocessor/bss-seg.md)|  
|[check_stack](../preprocessor/check-stack.md)|[code_seg](../preprocessor/code-seg.md)|[Açıklama](../preprocessor/comment-c-cpp.md)|  
|[component](../preprocessor/component.md)|[uygun](../preprocessor/conform.md) <sup>1</sup>|[const_seg](../preprocessor/const-seg.md)|  
|[data_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect_mismatch](../preprocessor/detect-mismatch.md)|  
|[fenv_access](../preprocessor/fenv-access.md)|[float_control](../preprocessor/float-control.md)|[fp_contract](../preprocessor/fp-contract.md)|  
|[İşlevi](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include_alias](../preprocessor/include-alias.md)|  
|[init_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline_depth](../preprocessor/inline-depth.md)|[inline_recursion](../preprocessor/inline-recursion.md)|  
|[intrinsic](../preprocessor/intrinsic.md)|[döngü](../preprocessor/loop.md) <sup>1</sup>|[make_public](../preprocessor/make-public.md)|  
|[Yönetilen](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||  
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||  
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers_to_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|  
|[pop_macro](../preprocessor/pop-macro.md)|[push_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|  
|[runtime_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|  
|[strict_gs_check](../preprocessor/strict-gs-check.md)|[Yönetilmeyen](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|  
|[warning](../preprocessor/warning.md)|||  
  
 1. Yalnızca C++ derleyicisi tarafından desteklenir.  
  
## <a name="pragmas-and-compiler-options"></a>Pragmaları ve derleyici seçenekleri  
 Bazı pragmaları derleyici seçenekleri ile aynı işlevselliği sağlar. Pragma kaynak kodunda karşılaşıldığında, derleyici seçeneği tarafından belirtilen davranışı geçersiz kılar. Örneğin, belirttiğiniz [/Zp8](../build/reference/zp-struct-member-alignment.md), kodla belirli bölümlerine için bu derleyici ayarı geçersiz kılabilirsiniz [paketi](../preprocessor/pack.md):  
  
```  
cl /Zp8 ...  
  
<file> - packing is 8  
// ...  
#pragma pack(push, 1) - packing is now 1  
// ...  
#pragma pack(pop) - packing is 8  
</file>  
```  
  
## <a name="the-pragma-keyword"></a>__Pragma() anahtar sözcüğü  
 **Belirli Microsoft**  
  
 Ayrıca, derleyicinin destekler `__pragma` aynı işlevselliğe sahip anahtar sözcüğü olarak `#pragma` yönergesi, ancak kullanılan satır bir makro tanımı içinde olabilir. `#pragma` Yönergesi çünkü derleyici numara işareti karakteri ('#') olmasını yönergesinde yorumlar makrosu tanımında kullanılamaz [dizeleyen işleç (#)](../preprocessor/stringizing-operator-hash.md).  
  
 Aşağıdaki kod örneğinde gösterilmektedir nasıl `__pragma` anahtar sözcüğü bir makro içinde kullanılabilir. Bu kod, "Derleyici COM destek örnekleri" içinde ACDUAL örneği mfcdual.h başlığından alınmıştır:  
  
```  
#define CATCH_ALL_DUAL \  
CATCH(COleException, e) \  
{ \  
_hr = e->m_sc; \  
} \  
AND_CATCH_ALL(e) \  
{ \  
__pragma(warning(push)) \  
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \  
AFX_MANAGE_STATE(pThis->m_pModuleState); \  
__pragma(warning(pop)) \  
_hr = DualHandleException(_riidSource, e); \  
} \  
END_CATCH_ALL \  
return _hr; \  
```  
  
 **Microsoft özel bitiş**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)   
 [C pragmaları](../c-language/c-pragmas.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)