---
title: Bağlayıcı Araçları Hatası LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: b18a93c7434ee3d66f42829f373bd916a65369bd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195181"
---
# <a name="linker-tools-error-lnk1188"></a>Bağlayıcı Araçları Hatası LNK1188

BADFIXUPSECTION:: geçersiz düzeltme hedefi ' sembol '; olası sıfır uzunluk bölümü

Bir VxD bağlantısı sırasında, bir yeniden konumlandırma hedefinin bir bölümü yoktu. LINK386 (daha eski bir sürüm) ile, bir OMF grup kaydı (MASı GROUP Direktifi tarafından oluşturulan), sıfır uzunluklu bölümü sıfır olmayan bir uzunluk bölümüyle birleştirmek için kullanılmış olabilir. COFF biçimi, Grup yönergesini ve sıfır uzunluklu bölümleri desteklemez. BAĞLANTı, bu tür OMF nesnelerini COFF 'ye otomatik olarak dönüştürdüğünde, bu hata ortaya çıkabilir.
