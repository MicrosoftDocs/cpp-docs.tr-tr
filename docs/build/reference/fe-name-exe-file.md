---
title: "-Fe (EXE dosyasını Adlandır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /fe
dev_langs: C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b66c473c49527dff395d206594a314b527c4f914
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fe-name-exe-file"></a>/Fe (EXE Dosyasını Adlandır)
Bir adı ve DLL derleyici tarafından oluşturulan ve .exe dosyası için bir dizini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Fepathname  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek derleyici dosya temel dosyasının adı ve uzantısı .exe veya .dll komut satırı üzerinde belirtilen ilk kaynak ya da nesne kullanarak varsayılan adı sağlar.  
  
 Belirtirseniz[/c (derleme olmadan bağlama)](../../build/reference/c-compile-without-linking.md), bağlama olmadan derlemek için **/Fe** hiçbir etkisi olmaz.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **genel**özellik sayfası.  
  
4.  Değiştirme **çıktı dosyası** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını derler ve geçerli dizindeki tüm C kaynak dosyaları bağlar. Sonuçta elde edilen yürütülebilir dosyasını PROCESS.exe olarak adlandırılır ve C:\BIN dizinde oluşturulur.  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırı yürütülebilir bir dosya oluşturur `C:\BIN` ilk kaynak ya da nesne dosyası ile aynı temel adla:  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yol adını belirtme](../../build/reference/specifying-the-pathname.md)