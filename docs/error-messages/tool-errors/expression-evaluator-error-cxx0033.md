---
title: İfade Değerlendirici Hatası CXX0033
ms.date: 11/04/2016
f1_keywords:
- CXX0033
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
ms.openlocfilehash: 8563eb2fbc24c6ad8db639d2e227802412a16090
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642799"
---
# <a name="expression-evaluator-error-cxx0033"></a>İfade Değerlendirici Hatası CXX0033

OMF tür bilgisi hatalı

Yürütülebilir dosya hata ayıklama için bir geçerli nesne modülü biçimi (OMF) sahip değil.

Bu hata için CAN0033 aynıdır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Visual C++'ın bu sürümü ile sunulan bağlayıcı yürütülebilir dosyası oluşturulmadı. Nesne kodu LINK.exe geçerli sürümünü kullanarak yeniden bağlayın.

1. .Exe dosyası bozulmuş olabilir. Yeniden derleyin ve programı yeniden bağlayın.