---
description: 'Daha fazla bilgi edinin: Ifade değerlendirici hatası CXX0015'
title: İfade Değerlendirici Hatası CXX0015
ms.date: 11/04/2016
f1_keywords:
- CXX0015
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
ms.openlocfilehash: c5d6e0ba5407646b1e3c835053f1f115dabf4fe7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228332"
---
# <a name="expression-evaluator-error-cxx0015"></a>İfade Değerlendirici Hatası CXX0015

ifade çok karmaşık (yığın taşması)

Girilen ifade çok karmaşıktı veya C ifadesi değerlendiricisi tarafından kullanılabilen depolama miktarı için çok derin iç içe geçmiş.

Taşma genellikle çok fazla bekleyen hesaplama nedeniyle oluşur.

İfadenin her bileşeni, ifadenin diğer bölümlerinin hesaplanmasını beklemek zorunda kalmak yerine, ifadenin her bileşeninin karşılaştığı şekilde değerlendirilebilmesi için ifadeyi yeniden düzenleyin.

İfadeyi birden çok komuta bölün.

Bu hata CAN0015 ile aynıdır.
