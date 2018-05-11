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
ms.openlocfilehash: 9a5ecfc9cc63fc4028e1f93d8f30e8d5cb9f9357
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
# <a name="ifdef-and-ifndef-directives-cc"></a>#ifdef ve #ifndef Yönergeleri (C/C++)
**#İfdef** ve **#ifndef** yönergeleri gibi aynı görevi gerçekleştirmek `#if` ile kullanıldığında yönergesi **tanımlanan**( *tanımlayıcısı* ).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz **#ifdef** ve **#ifndef** herhangi bir yere yönergeleri `#if` kullanılabilir. **#İfdef** *tanımlayıcısı* deyimi eşdeğerdir `#if 1` zaman *tanımlayıcısı* tanımlanmış, ve eşdeğer olan `#if 0` zaman *tanımlayıcısı* tanımlanmamış veya ile tanımsız `#undef` yönergesi. Bu yönergeleri yalnızca olup olmadığını denetlemek veya tanımlayıcıları yokluğu ile tanımlanan `#define`, C veya C++ kaynak kodunda bildirilen tanımlayıcıları için.  
  
 Bu yönergeleri yalnızca dil önceki sürümleriyle uyumluluk için sağlanır. **Tanımlı (** *tanımlayıcısı* **)** ile kullanılan sabit ifade `#if` yönergesi, tercih edilen yöntemdir.  
  
 **#İfndef** yönergesi olup olmadığını denetler tarafından kontrol koşul karşıtı **#ifdef**. Tanımlayıcı tanımlanmamış varsa (veya tanımına sahip kaldırılmış `#undef`), koşul değeri true (sıfır). Aksi takdirde, koşul yanlış olduğunda (0).  
  
 **Microsoft özel**  
  
 *Tanımlayıcısı* /D seçeneğini kullanarak komut satırından geçirilebilir. En fazla 30 makroları /D. ile belirtilebilir.  
  
 Bu, bir tanım komut satırından geçirilebilir çünkü bir tanım var olup olmadığını denetlemek için kullanışlıdır. Örneğin:  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)