---
title: "-FUNCTIONPADMIN (düzeltme eki eklenebilen görüntü oluşturma) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /functionpadmin
dev_langs: C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f737cdb412420ffb87664024b2314941e67b045b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Düzeltme Eki Eklenebilen Görüntü Oluşturma)
Görüntü için anında hazırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `space`(isteğe bağlı)  
 Her işlev başlangıcına eklemek için doldurma miktarı 5, 6 veya 16.  x86 görüntüleri beş bayt doldurma, görüntüleri gerektiren 6 bayt ve Itanium işlemci ailesi için oluşturulmuş görüntülerin gerektiren her işlevi başındaki doldurma 16 bayt x64 gerektirir.  
  
 Varsayılan olarak, görüntünün makine türüne göre görüntüye doğru miktarını derleyici ekleyeceksiniz.  
  
 Düzeltme eki eklenebilen görüntü üretmek bağlayıcı için sırayla .obj dosyaları ile derlenmiştir gerekir [/hotpatch (düzeltme eki eklenebilen görüntü oluşturma)](../../build/reference/hotpatch-create-hotpatchable-image.md).  
  
 Derleme ve cl.exe, tek bir çağrı görüntüyle bağlantı **/hotpatch** gelir **/functionpadmin**.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçenek içine türünü **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)