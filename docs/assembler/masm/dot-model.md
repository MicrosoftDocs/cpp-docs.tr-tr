---
title: . MODEL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .MODEL
dev_langs: C++
helpviewer_keywords: .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6d4ea26a75d37e264344aaacfa660e6d66dc8d5e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="model"></a>.MODEL
Program bellek modeli başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memorymodel`  
 Kod ve veri işaretçileri boyutunu belirleyen gerekli parametre.  
  
 `langtype`  
 Yordamlar ve genel semboller için arama ve adlandırma kuralları ayarlar isteğe bağlı parametre.  
  
 `stackoption`  
 İsteğe bağlı parametre.  
  
 `stackoption`kullanılmaz `memorymodel` olan `FLAT`.  
  
 Belirtme `NEARSTACK` yığın kesiminin tek bir fiziksel kesimde groups (`DGROUP`) veri yanı sıra. Yığın segment kayıt (`SS`) veri kesimi kayıt aynı adresine tutacak varsayılır (`DS`). `FARSTACK`yığın ile gruplandırmaz `DGROUP`; böylece `SS` eşit değil `DS`.  
  
## <a name="remarks"></a>Açıklamalar  
 .`MODEL` kullanılmaz [x64 (ml64.exe) için MASM](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 Aşağıdaki tabloda, 16 bit ve 32-bit platformu hedeflerken her parametresi için olası değerler listelenmektedir:  
  
|Parametre|32 bit değerleri|16 bit değerleri (önceki 16 bit geliştirme desteği)|  
|---------------|--------------------|----------------------------------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|Kullanılan değil|`NEARSTACK`, `FARSTACK`|  
  
## <a name="code"></a>Kod  
 MASM ile ilgili örnekler için derleyici örneklerini indirin [Visual C++ örnekleri ve ilgili belgeler için Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkID=178749).  
  
 Aşağıdaki örnek kullanımını gösteren `.MODEL` yönergesi.  
  
## <a name="example"></a>Örnek  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
ifndef X64  
.686p  
.XMM  
.model flat, C  
endif  
  
.data  
; user data  
  
.code  
; user code  
  
fxn PROC public  
  xor eax, eax ; zero function return value  
  ret  
fxn ENDP  
  
end  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)   
 [Visual C++ örnekleri ve Visual Studio 2010 için ilgili belgeler](http://go.microsoft.com/fwlink/?LinkID=178749)