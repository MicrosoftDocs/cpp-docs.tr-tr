---
title: "Derleyici Hatası C2732 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2732
dev_langs: C++
helpviewer_keywords: C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 38b364ac890118ce90164c3003a76e0d3c2e100d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2732"></a>Derleyici Hatası C2732
Önceki belirtimi 'function' için bağlantı belirtimi çelişir  
  
 İşlevi ile farklı bağlantı tanımlayıcısı zaten bildirildi.  
  
 Bu hatanın nedeni farklı bağlantı tanımlayıcıları dosyalarıyla vardır.  
  
 Bu hatayı düzeltmek için değiştirme `extern` deyimleri böylece raporlarınız kabul etmiş olursunuz. Özellikle, değil kaydırma `#include` yönergeleri `extern "C"` engeller.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2732 oluşturur:  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```