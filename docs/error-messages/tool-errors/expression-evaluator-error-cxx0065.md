---
title: İfade Değerlendirici Hatası CXX0065
ms.date: 11/04/2016
f1_keywords:
- CXX0065
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
ms.openlocfilehash: b4120deec3c8e7ce14e381f782904cf83a588e43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80184430"
---
# <a name="expression-evaluator-error-cxx0065"></a>İfade Değerlendirici Hatası CXX0065

değişken, yığın çerçevesine ihtiyaç duyuyor

Bir ifade, geçerli kapsam içinde bulunan ancak henüz oluşturulmamış bir değişken içeriyordu.

Bu hata, bir işlevin giriş sayfasına bir sözcük eklediğinizde ancak işlev için yığın çerçevesini ayarlamanıza veya işlev için çıkış koduna busaydıysanız oluşabilir.

İfadeyi değerlendirmeden önce yığın çerçevesi ayarlanana kadar giriş kodunu adım adım yapın.

Bu hata CAN0065 ile aynıdır.
