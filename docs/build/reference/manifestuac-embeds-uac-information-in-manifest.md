---
title: "-MANIFESTUAC (bildirimdeki UAC bilgilerini katıştırır) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
dev_langs: C++
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 564c17336936866750d05137a7bcd101b3a6534d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (Bildirimdeki UAC bilgilerini katıştırır)
Kullanıcı Hesabı Denetimi (UAC) bilgisi program bildiriminde ekli olup olmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fragment`  
 İçeren bir dize `level` ve `uiAccess` değerleri. Daha fazla bilgi için bu konunun ilerleyen bölümlerinde Açıklamalar bölümüne bakın.  
  
 `_level`  
 Aşağıdakilerden birini *asInvoker*, *highestAvailable*, veya *requireAdministrator'a*. Varsayılan olarak asInvoker. Daha fazla bilgi için bu konunun ilerleyen bölümlerinde Açıklamalar bölümüne bakın.  
  
 `_uiAccess`  
 `true`uygulamanın kullanıcı arabirimi koruma düzeyleri atlamak ve giriş izni daha yüksek Windows masaüstünde sürücü istiyorsanız; Aksi takdirde `false`. Varsayılan olarak `false`. Kümesine `true` yalnızca kullanıcı arabirimi erişilebilirlik uygulamaları için.  
  
## <a name="remarks"></a>Açıklamalar  
 Komut satırında birden çok /MANIFESTUAC seçeneği belirtirseniz, girilen sonuncu önceliklidir.  
  
 /MANIFESTUAC:level seçenekleri aşağıdaki gibidir:  
  
-   `asInvoker`: Uygulama aynı izinleri başlatıldığından bir işlem olarak çalışır. Uygulama daha yüksek bir izin düzeyi seçerek yükseltilebilir **yönetici olarak çalıştır**.  
  
-   highestAvailable: uygulama dağıtabilirsiniz bir en yüksek izin düzeyi ile çalışır. Uygulama başlatan kullanıcının Administrators grubunun bir üyesiyse, bu seçenek requireAdministrator'a ile aynıdır. Yüksek kullanılabilir izin düzeyini açılışı düzeyinden daha yüksek ise, sistem için kimlik bilgilerini ister.  
  
-   requireAdministrator'a: uygulama yönetici izinlerine sahip çalışır. Uygulama başlatan kullanıcının Yöneticiler grubunun bir üyesi olması gerekir. Açma işlemi yönetim izinleriyle çalışmıyorsa, sistemi için kimlik bilgilerini ister.  
  
 /MANIFESTUAC:fragment seçeneğini kullanarak tek bir adımda düzeyi ve UIAccess değerlerini belirtebilirsiniz. Parça şu biçimde olmalıdır:  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **bildirim dosyası** özellik sayfası.  
  
5.  Değiştirme **etkinleştirme kullanıcı hesabı denetimi (UAC)**, **UAC yürütme düzeyini**, ve **UAC atlama UI koruma** özellikleri.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A>, ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)