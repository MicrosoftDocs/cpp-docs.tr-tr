---
title: "Öznitelik bağlamları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: attributes [C++], contexts
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fceb15c713eee25c4ae04ef2a095737e587170a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [C++ öznitelikleri başvurusu](../windows/cpp-attributes-reference.md)