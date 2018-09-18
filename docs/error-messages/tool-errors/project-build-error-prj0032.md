---
title: Proje derleme hatası PRJ0032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0032
dev_langs:
- C++
helpviewer_keywords:
- PRJ0032
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 106b1c3f470bbdb134a5fd53ebaef65a4392fd4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053582"
---
# <a name="project-build-error-prj0032"></a>Proje Derleme Hatası PRJ0032

Proje düzeyindeki özel derleme adımı için 'Outputs' özelliğini 'out 'için macro_expansion' sonucunu veren makrosu' içeriyor.

Özel derleme adımı bir proje üzerinde büyük olasılıkla bir makro değerlendirme sorunu nedeniyle hatalı çıkış vardı. Bu hata, da yolu yanlış, karakter veya bir dosya yolunda geçersiz karakter birleşimlerinin içeren biçimlendirildiğini anlamına gelebilir.

Bu hatayı gidermek için makro düzeltin veya yolunu düzeltin. Proje dizininden mutlak bir yol değerlendirilen yoludur.