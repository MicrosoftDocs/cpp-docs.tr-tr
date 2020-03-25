---
title: İfade Değerlendirici Hatası CXX0030
ms.date: 11/04/2016
f1_keywords:
- CXX0030
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
ms.openlocfilehash: 477ec31d18924e91baf2d8b7b732bc7a50eee53b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195623"
---
# <a name="expression-evaluator-error-cxx0030"></a>İfade Değerlendirici Hatası CXX0030

ifade evaluatable değil

Hata ayıklayıcının ifade değerlendiricisi, yazılı olarak ifade için bir değer alamadı. Bunun olası nedenlerinden biri, ifadenin programın adres alanının dışında kalan belleğe (bir null işaretçi başvurusu, bir örnektir) başvuruyor olması olabilir. Windows, programın adres alanının dışında kalan belleğe erişime izin vermez.

Değerlendirme sırasını denetlemek için, ayraçları parantez kullanarak yeniden yazmak isteyebilirsiniz.

Bu hata CAN0030 ile aynıdır.
