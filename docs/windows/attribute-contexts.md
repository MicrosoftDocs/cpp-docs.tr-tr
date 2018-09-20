---
title: Öznitelik bağlamları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], contexts
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f34fb2a019e922f7eed3a430e62be272f9d57dce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427296"
---
# <a name="attribute-contexts"></a>Öznitelik Bağlamları
C++ öznitelikleri, dört temel alan kullanarak tanımlanabilen: Bunlar uygulanabilir hedef (**uygulanacağı**), tekrarlanabilir olsalar da (**Repeatable**), diğer öznitelikleri (varlığınıgerekli **Gerekli öznitelik**) ve diğer özniteliklerini uyumsuzluklar (**geçersiz öznitelikler**). Bu alanlar, her özniteliğin başvuru konusu eşlik eden bir tabloda listelenir. Bu alanların her biri aşağıda açıklanmıştır.
  
## <a name="applies-to"></a>Uygulandığı öğe:

Bu alan, belirtilen öznitelik için yasal hedefleri olan farklı C++ dil öğeleri açıklar. Örneğin, "class" bir öznitelik belirtir, **uygulanacağı** alan, bu gösterir öznitelik yalnızca geçerli bir C++ sınıfı için uygulanabilir. Öznitelik bir sınıfın bir üye işlevine uygulandığında sözdizimi hatası neden olur.
  
Daha fazla bilgi için [kullanıma göre öznitelikler](../windows/attributes-by-usage.md).
  
## <a name="repeatable"></a>Tekrarlanabilir

Bu alan özniteliği aynı hedefe art arda uygulanabilir olup olmadığını belirtir. Özniteliklerin çoğu tekrarlanabilir değildir.
  
## <a name="required-attributes"></a>Gerekli öznitelikleri

Bu alan olması gereken diğer özniteliklerini listeler (yani aynı hedefe) düzgün çalışması belirtilen öznitelik varsa. Bu alan herhangi bir giriş bir öznitelik için seyrek.
  
## <a name="invalid-attributes"></a>Geçersiz öznitelikler

Bu alan, belirtilen bir öznitelik ile uyumsuz olan diğer öznitelikleri listeler. Bu alan herhangi bir giriş bir öznitelik için seyrek.
  
## <a name="see-also"></a>Ayrıca Bkz.

[C++ Öznitelikleri Başvurusu](../windows/cpp-attributes-reference.md)