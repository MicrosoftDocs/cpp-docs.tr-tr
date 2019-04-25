---
title: Bağlayıcı Araçları Hatası LNK1188
ms.date: 11/04/2016
f1_keywords:
- LNK1188
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
ms.openlocfilehash: 69ac20522aebb7391319c0de210e06b305f3fd0d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226484"
---
# <a name="linker-tools-error-lnk1188"></a>Bağlayıcı Araçları Hatası LNK1188

BADFIXUPSECTION:: Geçersiz düzeltme hedefi 'symbol'; olası sıfır uzunluk bölümü

VxD bağlantı sırasında bir konum değiştirme hedefi bir bölümü yok. LINK386 ile (eski bir sürümü), bir OMF Grup kaydı (MASM grubu yönergesi tarafından oluşturulan) sıfır uzunluk bölümü başka bir sıfır uzunluk bölümü ile birleştirmek için kullanılmış olabilir. COFF biçimi GROUP yönergesi ve sıfır uzunluklu bölümlerin desteklemez. BAĞLANTI otomatik olarak bu tür bir OMF nesnelerini COFF dönüştürülürken, bu hata oluşabilir.