---
title: Derleyici Hatası C3505 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3505
dev_langs:
- C++
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e0ea8edd3237db2085365450f43b4b955d36f33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3505"></a>Derleyici Hatası C3505

> tür kitaplığı yüklenemiyor '*GUID*'  
  
32-bit, x86 barındırılan çapraz derleyici 64 bit çalıştırıyorsanız C3505 neden olabilir, 32-bit kayıt defteri kovanından hedefleri 64 bit derleyici WOW64 altında çalıştığı için makine ve yalnızca x64 okuyun.  
  
Tür kitaplığı içeri aktarmayı denediğiniz 32-bit ve 64 bit sürümlerini oluşturarak bu hatayı gidermek ve her ikisinin de kaydedin.  Veya değiştirmek gerektirir yerel 64 bit derleyici kullanabilirsiniz, **VC ++ dizinleri** 64 bit derleyici işaret edecek şekilde IDE'de özelliği.  
  
Daha fazla bilgi için bkz:  
  
-   [Nasıl yapılır: Komut Satırında 64 Bit Visual C++ Araç Takımını Etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [Nasıl Yapılır: Visual C++ Projelerinin 64 Bit, x64 Platformları Hedeflemesi için Yapılandırma](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)