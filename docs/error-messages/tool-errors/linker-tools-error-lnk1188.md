---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1188'
title: Bağlayıcı Araçları Hatası LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: 1bd826c3734d8079b370712ae829a0d0fb1abded
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321845"
---
# <a name="linker-tools-error-lnk1188"></a>Bağlayıcı Araçları Hatası LNK1188

BADFIXUPSECTION:: geçersiz düzeltme hedefi ' sembol '; olası sıfır uzunluk bölümü

Bir VxD bağlantısı sırasında, bir yeniden konumlandırma hedefinin bir bölümü yoktu. LINK386 (daha eski bir sürüm) ile, bir OMF grup kaydı (MASı GROUP Direktifi tarafından oluşturulan), sıfır uzunluklu bölümü sıfır olmayan bir uzunluk bölümüyle birleştirmek için kullanılmış olabilir. COFF biçimi, Grup yönergesini ve sıfır uzunluklu bölümleri desteklemez. BAĞLANTı, bu tür OMF nesnelerini COFF 'ye otomatik olarak dönüştürdüğünde, bu hata ortaya çıkabilir.
