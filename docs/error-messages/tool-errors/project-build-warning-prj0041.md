---
title: Proje Derleme Uyarısı PRJ0041
ms.date: 11/04/2016
f1_keywords:
- PRJ0041
helpviewer_keywords:
- PRJ0041
ms.assetid: dc9f4cf9-6bd5-4222-89e8-7802a59bb96b
ms.openlocfilehash: bb6469b1daf193223a9b3361cc3e4bfb96d0c751
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191944"
---
# <a name="project-build-warning-prj0041"></a>Proje Derleme Uyarısı PRJ0041

' File ' dosyası için eksik ' Dependency ' bağımlılığı bulunamıyor. Projeniz yine de oluşturulabilir, ancak bu dosya bulunana kadar güncel görülmeye devam edebilir.

Bir dosya (örneğin, kaynak dosyası veya. IDL/. odl dosyası), proje sisteminin çözemediği bir içerme ifadesini içeriyordu.

Proje sistemi önişlemci deyimlerini (örneğin #if) işlemediğinden, sorunlu deyim gerçekte derleme kapsamında olmayabilir.

Bu uyarıyı çözmek için,. RC dosyalarındaki tüm gereksiz kodu silin veya uygun adın yer tutucu dosyalarını ekleyin.
