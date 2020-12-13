---
description: 'Hakkında daha fazla bilgi edinin: proje derleme hatası PRJ0006'
title: Proje Derleme Hatası PRJ0006
ms.date: 11/04/2016
f1_keywords:
- PRJ0006
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
ms.openlocfilehash: a78646c843a6c6df3b4e2847076670492a9efb6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343931"
---
# <a name="project-build-error-prj0006"></a>Proje Derleme Hatası PRJ0006

Geçici dosya ' dosya ' açılamadı. Dosyanın var olduğundan ve dizinin yazma korumalı olmadığından emin olun.

Visual C++, derleme işlemi sırasında geçici bir dosya oluşturamadı. Bunun nedenleri şunlardır:

- Geçici dizin yok.

- Salt okuma geçici dizini.

- Disk alanı yetersiz.

- $ (IntDir) klasörü salt okunurdur veya salt okunan geçici dosyaları içerir.

Bu hata şu hata durumunda da PRJ0007: ' Dizin ' çıkış dizini oluşturulamadı. Error PRJ0007, $ (Int32) dizininin oluşturulamadığını, geçici olarak dosyaların oluşturulmasını da başarısız olacağını belirtir.

Geçici dosyalar her belirttiğinizde oluşturulur:

- Yanıt dosyası.

- Özel bir yapı adımı.

- Derleme olayı.
