---
title: "-vmb, - vmg (temsil yöntemi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /vmb
- /vmg
dev_langs: C++
helpviewer_keywords:
- vmb compiler option [C++]
- -vmg compiler option [C++]
- vmg compiler option [C++]
- -vmb compiler option [C++]
- /vmb compiler option [C++]
- representation method compiler options [C++]
- /vmg compiler option [C++]
ms.assetid: ecdb391c-7dab-40b1-916b-673d10889fd4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 061943dc029a566b7bc636a2bb4b37e276413245
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vmb-vmg-representation-method"></a>/vmb, /vmg (Temsil Yöntemi)
Derleyici sınıfı üyeleri işaretçileri göstermek için kullandığı yöntemi seçin.  
  
 Kullanım **/vmb** sınıf üyesi için bir işaretçi bildirme önce her zaman bir sınıfı tanımlamanız durumunda.  
  
 Kullanım **/vmg** sınıfı tanımlamadan önce bir sınıf üyesi için bir işaretçi bildirmek için. Üyeleri birbirine başvuru iki farklı sınıflarda tanımlarsanız, bu gereksinimi ortaya çıkabilir. Tanımlanmadan önce karşılıklı başvuru bu tür sınıflar için bir sınıf başvurulmuş olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/vmb  
/vmg  
```  
  
## <a name="remarks"></a>Açıklamalar  
 De kullanabilirsiniz [pointers_to_members](../../preprocessor/pointers-to-members.md) veya [devralınan anahtar sözcükler](../../cpp/inheritance-keywords.md) kodunuzda bir işaretçi gösterimi belirtin.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)