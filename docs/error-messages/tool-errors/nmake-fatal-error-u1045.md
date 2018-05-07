---
title: NMAKE önemli hatası U1045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1045
dev_langs:
- C++
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 673b20dde7156025c6aa56c487433eebe9e77aa3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE Önemli Hatası U1045
spawn başarısız oldu: ileti  
  
 Bir program veya komut belirli bir nedenle başarısız NMAKE tarafından çağrılır. NMAKE başka bir program çağırdığında — Örneğin, derleyici veya bağlayıcı — çağrısı başarısız olabilir veya bir hata çağrılan program tarafından döndürülebilir. Bu hatayı bildirmek için kullanılır.  
  
 Bu sorunu gidermek için öncelikle hatanın nedenini belirleyin. NMAKE tarafından bildirilen komutlarını kullanabilirsiniz [/N](../../build/nmake-options.md) ortam ayarları doğrulayın ve komut satırında NMAKE tarafından gerçekleştirilen eylemler yinelenecek seçeneği.