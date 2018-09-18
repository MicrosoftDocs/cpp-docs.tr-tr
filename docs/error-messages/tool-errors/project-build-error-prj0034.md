---
title: Proje derleme hatası PRJ0034 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0034
dev_langs:
- C++
helpviewer_keywords:
- PRJ0034
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b271875173bf0e55d94989d60a1c8f7aaf408b2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065588"
---
# <a name="project-build-error-prj0034"></a>Proje Derleme Hatası PRJ0034

Proje düzeyindeki özel 'Ek bağımlılıklar' özelliği 'out 'için macro_expansion' sonucunu veren yer alan adım makrosu' oluşturun.

Özel derleme adımı bulunan bir projede hata büyük olasılıkla bir makro değerlendirme sorunu nedeniyle ek bağımlılık içeriyor. Bu hata, da yolu yanlış, karakter veya bir dosya yolunda geçersiz karakter birleşimlerinin içeren biçimlendirildiğini anlamına gelebilir.

Bu hatayı gidermek için makro düzeltin veya yolunu düzeltin. Proje dizininden mutlak bir yol değerlendirilen yoludur.