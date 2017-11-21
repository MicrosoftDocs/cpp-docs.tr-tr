---
title: 1.4 uyumluluk | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d8481c0efb54a397db004f321fb48c217cba8ebc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="14-compliance"></a>1.4 Uyumluluk
OpenMP C/C++ API uygulamasıdır *OpenMP uyumlu* tanır ve bu belirtimi tüm öğeleri semantiği bölüm 1, 2, 3, 4, düzenlendiği şekilde korur ve ek c ekler A, B, D, E ve F içindir bilgiler yalnızca amacıyla ve belirtiminin bir parçası değildir. Yalnızca bir alt API dahil uygulamaları OpenMP uyumlu değildir.  
  
 OpenMP C ve C++ API uygulaması tarafından desteklenen temel dil için bir uzantısıdır. Temel dil bu belgede bir dil yapısı veya görünür uzantısı desteklemiyorsa, OpenMP uygulaması bunu desteklemek için gerekli değildir.  
  
 Tüm standart C ve C++ Kitaplık işlevleri ve yerleşik işlevler (diğer bir deyişle, derleyici belirli bilgi olan işlevler) iş parçacığı açısından güvenli olması gerekir. İş parçacığı işlevleri paralel bir bölge içinde farklı iş parçacıkları tarafından eşitlenmemiş kullanımını tanımsız davranış üretmez. Ancak, davranışı seri bölge ile aynı olmayabilir. (Bir rastgele sayı oluşturma işlevi bir örnektir.)  
  
 OpenMP C/C++ API belirli bir davranış belirtir *uygulama tanımlı.* Uyumlu bir OpenMP uygulaması tanımlamak ve bu gibi durumlarda davranışını belgelemek için gereklidir. Bkz: [ek E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), sayfa 97, uygulama tanımlı davranış listesi.