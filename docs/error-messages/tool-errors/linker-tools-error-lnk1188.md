---
title: "Bağlayıcı araçları hatası LNK1188 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1188
dev_langs: C++
helpviewer_keywords: LNK1188
ms.assetid: 4af574b0-5b41-4580-9a37-52a634add995
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a77f769aed208c557b72e12572d170482d2538ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1188"></a>Bağlayıcı Araçları Hatası LNK1188
BADFIXUPSECTION:: Geçersiz düzeltmesi hedef 'simge'; olası sıfır uzunluk bölümü  
  
 VxD bağlantı sırasında bir konumu değiştirme hedefi bir bölüme sahip değil. LINK386 ile (eski bir sürümü), (MASM Grup yönergesi tarafından oluşturulan) OMF grubu kaydı başka bir sıfır uzunluk bölüm sıfır uzunluk bölümle birleştirmek için kullanılmış. Sıfır uzunluklu bölümleri ve Grup yönergesi COFF biçimi desteklemiyor. BAĞLANTI otomatik olarak bu OMF nesne türleri COFF'ye dönüştürdüğünde, bu hata oluşabilir.