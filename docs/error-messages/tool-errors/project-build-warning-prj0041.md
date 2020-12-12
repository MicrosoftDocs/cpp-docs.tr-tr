---
description: 'Hakkında daha fazla bilgi edinin: proje derleme uyarısı PRJ0041'
title: Proje Derleme Uyarısı PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: dc6b36e052d3402f047257a4bf0035d7ec30f92a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206454"
---
# <a name="project-build-warning-prj0041"></a>Proje Derleme Uyarısı PRJ0041

' File ' dosyası için eksik ' Dependency ' bağımlılığı bulunamıyor. Projeniz yine de oluşturulabilir, ancak bu dosya bulunana kadar güncel görülmeye devam edebilir.

Bir dosya (örneğin, kaynak dosyası veya. IDL/. odl dosyası), proje sisteminin çözemediği bir içerme ifadesini içeriyordu.

Proje sistemi önişlemci deyimlerini (örneğin #if) işlemediğinden, sorunlu deyim gerçekte derleme kapsamında olmayabilir.

Bu uyarıyı çözmek için,. RC dosyalarındaki tüm gereksiz kodu silin veya uygun adın yer tutucu dosyalarını ekleyin.
