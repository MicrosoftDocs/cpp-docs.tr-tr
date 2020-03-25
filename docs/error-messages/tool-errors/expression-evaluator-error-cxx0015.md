---
title: İfade Değerlendirici Hatası CXX0015
ms.date: 11/04/2016
f1_keywords:
- CXX0015
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
ms.openlocfilehash: 19cf47d6b7b718eb19b987bcc16854af3266069b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196072"
---
# <a name="expression-evaluator-error-cxx0015"></a>İfade Değerlendirici Hatası CXX0015

ifade çok karmaşık (yığın taşması)

Girilen ifade çok karmaşıktı veya C ifadesi değerlendiricisi tarafından kullanılabilen depolama miktarı için çok derin iç içe geçmiş.

Taşma genellikle çok fazla bekleyen hesaplama nedeniyle oluşur.

İfadenin her bileşeni, ifadenin diğer bölümlerinin hesaplanmasını beklemek zorunda kalmak yerine, ifadenin her bileşeninin karşılaştığı şekilde değerlendirilebilmesi için ifadeyi yeniden düzenleyin.

İfadeyi birden çok komuta bölün.

Bu hata CAN0015 ile aynıdır.
