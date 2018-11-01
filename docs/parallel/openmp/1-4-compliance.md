---
title: 1.4 Uyumluluk
ms.date: 11/04/2016
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
ms.openlocfilehash: 7fb47c9989e971e10701c2ee2bd7ac7823141812
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642461"
---
# <a name="14-compliance"></a>1.4 Uyumluluk

OpenMP C/C++ API uygulamasıdır *OpenMP uyumlu* tanır ve bu belirtim tüm öğelerini semantiği olarak bölümlerde 1, 2, 3, 4, normal bir kutudur korur ve ek c ek A, B, D, E ve F içindir bilgiler yalnızca amacıyla ve belirtiminin parçası değildir. Yalnızca bir API alt kümesini içeren uygulamalar OpenMP uyumlu değildir.

OpenMP C ve C++ API uygulaması tarafından desteklenen temel dil için bir uzantısıdır. Temel dil dil yapısı veya görüntülenen uzantısı bu belgede desteklemiyorsa, OpenMP uygulaması bunu desteklemek için gerekli değildir.

Tüm standart C ve C++ Kitaplığı işlevleri ve yerleşik işlevler (diğer bir deyişle, İşlevler derleyici belirli bilgi olduğu) iş parçacığı açısından güvenli olması gerekir. Bir paralel bölgenin içinde farklı iş parçacıkları tarafından iş parçacığı açısından güvenli işlevlerin eşitlenmemiş kullanımını tanımsız davranış üretmez. Ancak, davranışı seri bir bölge ile aynı olmayabilir. (Bir rastgele sayı oluşturma işlevi, örnek verilebilir.)

OpenMP C/C++ API belirli bir davranış belirtir *uygulama tanımlı.* Uyumlu bir OpenMP uygulama tanımlamak ve bu gibi durumlarda davranışını belge için gereklidir. Bkz: [ek E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), sayfa 97, uygulama tanımlı davranışlar listesi.