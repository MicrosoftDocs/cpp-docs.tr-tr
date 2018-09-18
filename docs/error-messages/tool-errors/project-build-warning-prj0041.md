---
title: Proje derleme uyarısı PRJ0041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0041
dev_langs:
- C++
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7677c5718783065f64e52f98f7ddbed76e905d2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038145"
---
# <a name="project-build-warning-prj0041"></a>Proje Derleme Uyarısı PRJ0041

Eksik bulunamıyor bağımlılık 'dosya' dosyası için ' bağımlılığı'. Projeniz derlenmeye devam edebilir, ancak bu dosya bulunana kadar proje güncel sayılmayabilir devam edebilir.

Bir dosya (kaynak dosya veya.idl/.odl dosyası gibi yer alan, proje sistemi değil çözümlenemiyor INCLUDE deyimi.

Proje sistemi önişlemci deyimleri (örneğin, #if) işlemez olduğundan, soruna neden olan deyim aslında yapının bir parçası olmayabilir.

Bu uyarıyı çözmek için tüm gereksiz kodda .rc dosyaları silin veya uygun bir ad yer tutucusu dosyaları ekleyin.