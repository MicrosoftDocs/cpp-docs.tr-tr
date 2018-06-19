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
- attributes [C++], contexts
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e220eb0e7eb80d01d70aed82e773c46fe6704c7d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860339"
---
# <a name="attribute-contexts"></a>Öznitelik Bağlamları
C++ öznitelikleri dört temel alan kullanarak tanımlanabilen: Bunlar uygulanabilir hedef (**uygulandığı**), veya repeatable olmaları durumunda (**Repeatable**), diğer öznitelikleri (varlığınıgerekli **Gerekli öznitelikler**) ve diğer öznitelikleri uyumsuzluklar (**geçersiz öznitelikler**). Bu alanların her özniteliğin başvuru konusu eşlik eden bir tabloda listelenmiştir. Bu alanların her biri aşağıda açıklanmıştır.  
  
## <a name="applies-to"></a>Uygulandığı öğe:  
 Bu alan, yasal hedefler belirtilen özniteliği için farklı C++ Dil öğelerini açıklar. Örneğin, bir öznitelik olarak "sınıf" belirtiyorsa **uygulandığı** alan, bu gösterir özniteliği yalnızca yasal bir C++ sınıfa uygulanabilir. Öznitelik bir sınıf için bir üye işlevi uyguladıysanız, bir sözdizimi hatası neden olur.  
  
 Daha fazla bilgi için bkz: [kullanıma göre öznitelikler](../windows/attributes-by-usage.md).  
  
## <a name="repeatable"></a>Yinelenebilir  
 Bu alan özniteliği aynı hedefe art arda uygulanabilir olup olmadığını belirtir. Öznitelikleri çoğunluğu yinelenebilir değildir.  
  
## <a name="required-attributes"></a>Gerekli öznitelikler  
 Bu alan olması gereken diğer öznitelikleri listeler (yani aynı hedefe uygulanmış) düzgün çalışması belirtilen öznitelik varsa. Bu alan için herhangi bir giriş bir öznitelik için nadir bir durumdur.  
  
## <a name="invalid-attributes"></a>Geçersiz öznitelikler  
 Bu alanda belirtilen öznitelik uyumsuz diğer öznitelikleri listeler. Bu alan için herhangi bir giriş bir öznitelik için nadir bir durumdur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Öznitelikleri Başvurusu](../windows/cpp-attributes-reference.md)