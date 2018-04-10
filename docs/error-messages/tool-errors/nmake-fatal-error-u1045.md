---
title: NMAKE önemli hatası U1045 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- U1045
dev_langs:
- C++
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cdd9fb3d0bcee20e1952cea6444f586a9117365a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE Önemli Hatası U1045
spawn başarısız oldu: ileti  
  
 Bir program veya komut belirli bir nedenle başarısız NMAKE tarafından çağrılır. NMAKE başka bir program çağırdığında — Örneğin, derleyici veya bağlayıcı — çağrısı başarısız olabilir veya bir hata çağrılan program tarafından döndürülebilir. Bu hatayı bildirmek için kullanılır.  
  
 Bu sorunu gidermek için öncelikle hatanın nedenini belirleyin. NMAKE tarafından bildirilen komutlarını kullanabilirsiniz [/N](../../build/nmake-options.md) ortam ayarları doğrulayın ve komut satırında NMAKE tarafından gerçekleştirilen eylemler yinelenecek seçeneği.