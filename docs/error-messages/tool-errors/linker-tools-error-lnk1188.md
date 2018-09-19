---
title: Bağlayıcı araçları hatası LNK1188 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36b31590d94d809c16ed64d16071db0919f60238
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098946"
---
# <a name="linker-tools-error-lnk1188"></a>Bağlayıcı Araçları Hatası LNK1188

BADFIXUPSECTION:: Geçersiz düzeltme hedefi 'symbol'; olası sıfır uzunluk bölümü

VxD bağlantı sırasında bir konum değiştirme hedefi bir bölümü yok. LINK386 ile (eski bir sürümü), bir OMF Grup kaydı (MASM grubu yönergesi tarafından oluşturulan) sıfır uzunluk bölümü başka bir sıfır uzunluk bölümü ile birleştirmek için kullanılmış olabilir. COFF biçimi GROUP yönergesi ve sıfır uzunluklu bölümlerin desteklemez. BAĞLANTI otomatik olarak bu tür bir OMF nesnelerini COFF dönüştürülürken, bu hata oluşabilir.