---
title: "Derleyici Hatası C2030 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2030
dev_langs: C++
helpviewer_keywords: C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a2efd868160e3ec7e5bf356603cc821a0b07f149
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2030"></a>Derleyici Hatası C2030
yıkıcı Erişilebilirlik 'özel korumalı' ile 'Kapalı' olarak bildirilen bir sınıf üyesi olamaz  
  
 Windows çalışma zamanı sınıf olarak bildirilen `sealed` korumalı özel yıkıcı sahip olamaz. Yalnızca ortak sanal ve özel sanal olmayan Yıkıcılar korumalı türlerde izin verilir. Daha fazla bilgi için bkz: [Ref sınıflar ve yapılar](../../cppcx/ref-classes-and-structs-c-cx.md).  
  
 Bu hatayı düzeltmek için yıkıcı erişilebilirliğini değiştirin.