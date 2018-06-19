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
ms.openlocfilehash: e31943ae253a332576fba73102db410b103a0096
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302626"
---
# <a name="linker-tools-error-lnk1188"></a>Bağlayıcı Araçları Hatası LNK1188
BADFIXUPSECTION:: Geçersiz düzeltmesi hedef 'simge'; olası sıfır uzunluk bölümü  
  
 VxD bağlantı sırasında bir konumu değiştirme hedefi bir bölüme sahip değil. LINK386 ile (eski bir sürümü), (MASM Grup yönergesi tarafından oluşturulan) OMF grubu kaydı başka bir sıfır uzunluk bölüm sıfır uzunluk bölümle birleştirmek için kullanılmış. Sıfır uzunluklu bölümleri ve Grup yönergesi COFF biçimi desteklemiyor. BAĞLANTI otomatik olarak bu OMF nesne türleri COFF'ye dönüştürdüğünde, bu hata oluşabilir.