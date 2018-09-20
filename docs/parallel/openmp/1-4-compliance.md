---
title: 1.4 uyumluluk | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a332d8fb5de172c363c6f9c1bebba65d6fa0ff8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381822"
---
# <a name="14-compliance"></a>1.4 Uyumluluk

OpenMP C/C++ API uygulamasıdır *OpenMP uyumlu* tanır ve bu belirtim tüm öğelerini semantiği olarak bölümlerde 1, 2, 3, 4, normal bir kutudur korur ve ek c ek A, B, D, E ve F içindir bilgiler yalnızca amacıyla ve belirtiminin parçası değildir. Yalnızca bir API alt kümesini içeren uygulamalar OpenMP uyumlu değildir.

OpenMP C ve C++ API uygulaması tarafından desteklenen temel dil için bir uzantısıdır. Temel dil dil yapısı veya görüntülenen uzantısı bu belgede desteklemiyorsa, OpenMP uygulaması bunu desteklemek için gerekli değildir.

Tüm standart C ve C++ Kitaplığı işlevleri ve yerleşik işlevler (diğer bir deyişle, İşlevler derleyici belirli bilgi olduğu) iş parçacığı açısından güvenli olması gerekir. Bir paralel bölgenin içinde farklı iş parçacıkları tarafından iş parçacığı açısından güvenli işlevlerin eşitlenmemiş kullanımını tanımsız davranış üretmez. Ancak, davranışı seri bir bölge ile aynı olmayabilir. (Bir rastgele sayı oluşturma işlevi, örnek verilebilir.)

OpenMP C/C++ API belirli bir davranış belirtir *uygulama tanımlı.* Uyumlu bir OpenMP uygulama tanımlamak ve bu gibi durumlarda davranışını belge için gereklidir. Bkz: [ek E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), sayfa 97, uygulama tanımlı davranışlar listesi.