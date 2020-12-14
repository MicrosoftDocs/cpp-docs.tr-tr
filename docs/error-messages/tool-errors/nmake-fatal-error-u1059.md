---
description: 'Hakkında daha fazla bilgi edinin: NMAKE önemli hatası U1059'
title: NMAKE Önemli Hatası U1059
ms.date: 08/27/2018
f1_keywords:
- U1059
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
ms.openlocfilehash: 025ea8577814519b883e534c54ed8cf4383ef029
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283543"
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE Önemli Hatası U1059

> sözdizimi hatası: bağımlıda '} ' eksik

Bağımlı için bir arama yolu yanlış belirtildi. Yolda bir boşluk vardı ya da kapatma ayracı (**}**) atlandı.

Bir bağımlı için Dizin belirtiminin sözdizimi

> **{** *dizinler* **} bağımlı**

Burada *dizinler* , her biri noktalı virgül (**;**) ile ayrılmış bir veya daha fazla yol belirtir. Boşluklara izin verilmez.

Bir arama yolunun kısmı veya tümü makro ile değiştirilirse, makro genişletmesinde boşluk olmadığından emin olun.
