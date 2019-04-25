---
title: Proje Derleme Uyarısı PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: b0fceff05ffe35515965b7e0a880c8b4c941b07e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297729"
---
# <a name="project-build-warning-prj0041"></a>Proje Derleme Uyarısı PRJ0041

Eksik bulunamıyor bağımlılık 'dosya' dosyası için ' bağımlılığı'. Projeniz derlenmeye devam edebilir, ancak bu dosya bulunana kadar proje güncel sayılmayabilir devam edebilir.

Bir dosya (kaynak dosya veya.idl/.odl dosyası gibi yer alan, proje sistemi değil çözümlenemiyor INCLUDE deyimi.

Proje sistemi önişlemci deyimleri (örneğin, #if) işlemez olduğundan, soruna neden olan deyim aslında yapının bir parçası olmayabilir.

Bu uyarıyı çözmek için tüm gereksiz kodda .rc dosyaları silin veya uygun bir ad yer tutucusu dosyaları ekleyin.