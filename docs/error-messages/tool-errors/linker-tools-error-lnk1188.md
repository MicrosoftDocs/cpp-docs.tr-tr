---
title: "Bağlayıcı araçları hatası LNK1188 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1188
dev_langs:
- C++
helpviewer_keywords:
- LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81d2988742eb9e8cd6aef134510ac8272d3dd27c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1188"></a>Bağlayıcı Araçları Hatası LNK1188
BADFIXUPSECTION:: Geçersiz düzeltmesi hedef 'simge'; olası sıfır uzunluk bölümü  
  
 VxD bağlantı sırasında bir konumu değiştirme hedefi bir bölüme sahip değil. LINK386 ile (eski bir sürümü), (MASM Grup yönergesi tarafından oluşturulan) OMF grubu kaydı başka bir sıfır uzunluk bölüm sıfır uzunluk bölümle birleştirmek için kullanılmış. Sıfır uzunluklu bölümleri ve Grup yönergesi COFF biçimi desteklemiyor. BAĞLANTI otomatik olarak bu OMF nesne türleri COFF'ye dönüştürdüğünde, bu hata oluşabilir.