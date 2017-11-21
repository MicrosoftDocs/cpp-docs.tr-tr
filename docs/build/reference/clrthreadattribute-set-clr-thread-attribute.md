---
title: "-CLRTHREADATTRIBUTE (CLR iş parçacığı özniteliğini Ayarla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.CLRThreadAttribute
dev_langs: C++
helpviewer_keywords:
- /CLRTHREADATTRIBUTE linker option
- -CLRTHREADATTRIBUTE linker option
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e928d24c6257bc64303d667e66cd1f968e003450
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="clrthreadattribute-set-clr-thread-attribute"></a>/CLRTHREADATTRIBUTE (CLR İş Parçacığı Özniteliğini Ayarla)
Açıkça CLR programınızın giriş noktası için iş parçacığı özniteliğini belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### <a name="parameters"></a>Parametreler  
 MTA  
 MTAThreadAttribute özniteliği programınızın giriş noktası için geçerlidir.  
  
 YOK  
 /CLRTHREADATTRIBUTE belirtmeden aynıdır.  Threading özniteliği varsayılan ortak dil çalışma zamanı (CLR) sağlar.  
  
 STA  
 STAThreadAttribute özniteliği programınızın giriş noktası için geçerlidir.  
  
## <a name="remarks"></a>Açıklamalar  
 Ana iş parçacığı giriş noktasını etkileyen iş parçacığı özniteliğini yalnızca bir .exe oluştururken geçerli değil.  
  
 Kullanırsanız, varsayılan giriş noktası (ana veya örneğin wmain) /CLRTHREADATTRIBUTE kullanarak ya da iş parçacığı modelini belirtin veya koyarak iş parçacığı özniteliği (STAThreadAttribute veya MTAThreadAttribute) varsayılan giriş işlev.  
  
 Varsayılan olmayan giriş noktası kullanırsanız, /CLRTHREADATTRIBUTE kullanarak veya iş parçacığı yerleştirme özniteliği varsayılan olmayan giriş işlev ve varsayılan olmayan giriş noktasıyla belirtin iş parçacığı modelini belirtin [/Entry](../../build/reference/entry-entry-point-symbol.md) .  
  
 Belirtilen kaynak kodda iş parçacığı modelini /CLRTHREADATTRIBUTE ile belirtilen iş parçacığı modeliyle kabul etmezse, bağlayıcı /CLRTHREADATTRIBUTE yoksay ve kaynak kodunda belirtilen iş parçacığı modelini uygulayın.  
  
 CLR programınızı tek iş parçacığı kullanan bir COM nesnesi barındırıyorsa, örneğin, tek iş parçacıklı, kullanmanız için gerekli olacaktır.  Çoklu iş parçacığı kullanır, CLR program görüntüleniyorsa, tek iş parçacığı kullanan bir COM nesnesi barındıramaz.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **Gelişmiş** özellik sayfası.  
  
5.  Değiştirme **CLR iş parçacığı özniteliğini** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)