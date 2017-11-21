---
title: "Toplu iş modu kuralları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: be8c00009e285ec84f42ae6f53c578a3084432de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="batch-mode-rules"></a>Toplu İş Modu Kuralları
```  
{frompath}.fromext{topath}.toext::  
   commands  
```  
  
 Bu çıkarım kuralı N komutları çalışmaya başladığınızda toplu iş modu çıkarım kuralları çıkarım kuralı yalnızca bir çağrılmasını sağlar. Toplu iş modu çıkarım kuralları çağrılacak N komutları gerektirecektir. N çıkarım kuralı tetiklemek bağımlıları sayısıdır.  
  
 Toplu iş modu çıkarım kuralları içeren derleme görevleri dosyaları NMAKE 1.62 veya sonraki sürümünü kullanmanız gerekir. NMAKE sürümünü denetlemek için 1.62 ya da daha yüksek kullanılabilir _NMAKE_VER makrosu NMAKE sürümü ile çalıştırın. Bu makrosu Visual C++ ürün sürümü temsil eden bir dize döndürür.  
  
 Yalnızca söz dizimi standart çıkarım kuraldan toplu iş modu çıkarım kuralı çift iki nokta (:) ile sonlandırılır farktır.  
  
> [!NOTE]
>  Çağrılan aracı birden çok dosya kaldırabilir olmalıdır. Toplu iş modu çıkarım kuralı kullanmalısınız `$<` bağımlı dosyalara erişmek için makrosu olarak.  
  
 Toplu iş modu çıkarım kuralları oluşturma işlemini hızlandırabilir. Derleyici sürücüsü yalnızca bir kez çağrılır olduğundan toplu işlem derleyicide dosyalara sağlamak için daha hızlıdır. Örneğin, C ve C++ derleyicisi daha iyi bellek işlemi sırasında yerleşik kalabileceği çünkü dosyaları kümesini işlerken gerçekleştirir.  
  
 Aşağıdaki örnek, toplu iş modu çıkarım kuralları kullanmayı gösterir:  
  
```  
#  
# sample makefile to illustrate batch-mode inference rules  
#  
O = .  
S = .  
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj  
CFLAGS = -nologo  
  
all : $(Objs)  
  
!ifdef NOBatch  
{$S}.cpp{$O}.obj:  
!else  
{$S}.cpp{$O}.obj::  
!endif  
   $(CC) $(CFLAGS) -Fd$O\ -c $<  
  
$(Objs) :  
  
#end of makefile  
```  
  
 NMAKE toplu iş modu çıkarım kuralları olmadan şu çıkışı üretir:  
  
```  
E:\tmp> nmake -f test.mak -a NOBatch=1  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
        cl -nologo -Fd.\ -c .\foo1.cpp  
foo1.cpp  
        cl -nologo -Fd.\ -c .\foo2.cpp  
foo2.cpp  
        cl -nologo -Fd.\ -c .\foo3.cpp  
foo3.cpp  
        cl -nologo -Fd.\ -c .\foo4.cpp  
foo4.cpp  
```  
  
 NMAKE toplu iş modu çıkarım kuralları ile aşağıdaki sonucu üretir:  
  
```  
E:\tmp> nmake -f test.mak -a  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
  
        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp  
foo1.cpp  
foo2.cpp  
foo3.cpp  
foo4.cpp  
Generating Code...  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıkarım kuralları](../build/inference-rules.md)