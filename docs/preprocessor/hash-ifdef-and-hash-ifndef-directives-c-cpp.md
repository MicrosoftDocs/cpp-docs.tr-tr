---
title: '#ıfdef ve #ifndef yönergeleri (C/C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#ifndef'
- '#ifdef'
dev_langs:
- C++
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c3453cd652401e9d1f4573bb1750773cbefe8d9
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465154"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef ve #ifndef Yönergeleri (C/C++)
**#İfdef** ve **#ifndef** yönergeleri aynı görevi gerçekleştirmek `#if` ile kullanıldığında yönergesi **tanımlanan**( *tanımlayıcısı* ).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Kullanabileceğiniz **#ifdef** ve **#ifndef** yönergeleri her yerde `#if` kullanılabilir. **#İfdef** *tanımlayıcı* deyimi, `#if 1` olduğunda *tanımlayıcı* tanımlı ve eşdeğerdir `#if 0` olduğunda *tanımlayıcı* tanımlanmadı veya ile tanımlanmamış `#undef` yönergesi. Bu yönergeler yalnızca olup olmadığını denetleyin veya ile tanımlanan tanımlayıcıların devamsızlık `#define`, C veya C++ kaynak koduyla bildirilmiş olan tanımlayıcıları denetlemez.  
  
Bu yönergeler yalnızca dilin önceki sürümleriyle uyumluluk için sağlanır. **Tanımlanan (** *tanımlayıcı* **)** sabit ifade ile kullanılan `#if` yönergesi, tercih edilen yöntemdir.  
  
**#İfndef** yönergesi tarafından denetlenen koşulun tersini denetler **#ifdef**. Tanımlayıcı tanımlı değilse (veya tanımı ile kaldırılmış `#undef`), koşul true (sıfırdan farklı). Aksi halde koşul false (0).  
  
**Microsoft'a özgü**  
  
*Tanımlayıcı* kullanılarak komut satırından geçirilebilir `/D` seçeneği. En fazla 30 makro belirtilebilir `/D`.  
  
Bu, komut satırından bir tanım iletilebildiği bir tanımı mevcut olup olmadığını denetlemek için yararlıdır. Örneğin:  
  
```cpp  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)