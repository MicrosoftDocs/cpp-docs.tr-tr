---
title: Proje derleme hatası PRJ0008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0008
dev_langs:
- C++
helpviewer_keywords:
- PRJ0008
ms.assetid: 6bf7f17a-d2a8-4826-99c7-d600d846952f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7c24634a845423de590228af01cb9f4779e37ab
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062793"
---
# <a name="project-build-error-prj0008"></a>Proje Derleme Hatası PRJ0008

'Dosya' dosyası silinemedi.

**Dosya başka bir işlem tarafından açık olmadığından ve yazma korumalı olmadığından emin olun.**

Bir yeniden oluşturma sırasında veya temizleyen, Visual C++ derleme için tüm bilinen Ara ve Çıkış dosyalarını yanı sıra, joker karakter belirtimleri karşılayan tüm dosyaları siler. **uzantıları temizlemede** özelliğinde [genel Yapılandırma ayarları özellik sayfası](../../ide/general-property-page-project.md).

Visual C++ bir dosyayı silmek mümkün değilse bu hata iletisiyle karşılaşırsınız. Hatayı gidermek için dosya ve alt dizin yazılabilir derleme yapan kullanıcı için olun.