---
title: İfade değerlendirici hatası CXX0033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04f37b53c30d36a43d339132bfd9baca3e5ec70c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057205"
---
# <a name="expression-evaluator-error-cxx0033"></a>İfade Değerlendirici Hatası CXX0033

OMF tür bilgisi hatalı

Yürütülebilir dosya hata ayıklama için bir geçerli nesne modülü biçimi (OMF) sahip değil.

Bu hata için CAN0033 aynıdır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Visual C++'ın bu sürümü ile sunulan bağlayıcı yürütülebilir dosyası oluşturulmadı. Nesne kodu LINK.exe geçerli sürümünü kullanarak yeniden bağlayın.

1. .Exe dosyası bozulmuş olabilir. Yeniden derleyin ve programı yeniden bağlayın.