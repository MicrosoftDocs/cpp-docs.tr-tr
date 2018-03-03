---
title: "-vd (yapı yer devre dışı bırak) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /vd
dev_langs:
- C++
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b945c4a3191554d5299522ff376772d6362a616c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="vd-disable-construction-displacements"></a>/vd (Yapı Yer Değiştirmelerini Devre Dışı Bırak)
## <a name="syntax"></a>Sözdizimi  
  
```  
/vdn  
```  
  
## <a name="arguments"></a>Arguments  
 `0`  
 Vtordisp Oluşturucusu/yıkıcı öteleme üye gizler. Bu seçenek yalnızca tüm sınıf oluşturucular ve Yıkıcılar sanal çağrı eminseniz neredeyse işlevleri seçin.  
  
 `1`  
 Gizli vtordisp Oluşturucusu/yıkıcı öteleme üyeleri oluşturulmasını sağlar. Bu seçim varsayılandır.  
  
 `2`  
 Sayesinde [dynamic_cast işleci](../../cpp/dynamic-cast-operator.md) yapılandırılan bir nesne üzerinde. Örneğin, bir dynamic_cast sanal temel sınıfından türetilmiş bir sınıf için.  
  
 **/vd2** sanal temel sanal işlevlere sahip olduğunda vtordisp alan ekler. **/ vd1** yeterli olacaktır. En sık karşılaşılan durumda nerede **/vd2** gereklidir sanal tabanınızı yalnızca sanal işlevinde bir yıkıcı olur.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenekler yalnızca sanal tabanları kullanan C++ kodu için geçerlidir.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]C++ yapım öteleme destek sanal devralma kullanıldığı durumlarda uygular. Yapı yer oluşturulan bir sanal Bankası'nda bildirilir ve türetilen bir sınıfta geçersiz bir sanal işlev, sorunu çözmek, daha yeni olan türetilmiş bir sınıf oluşturma sırasında bir oluşturucusundan çağrılır.  
  
 Sanal işlev yanlış bir geçirilebilir olduğunu sorunudur `this` işaretçi sonucunda sanal yer arasında tutarsızlık, taban sınıf ve türetilmiş sınıflarının için yer. Vtordisp alan bir sınıf için her sanal temel olarak adlandırılan tek yapım öteleme ayarlama, çözümü sağlar.  
  
 Varsayılan olarak, kodu kullanıcı tanımlı oluşturucular ve Yıkıcılar tanımlar ve ayrıca sanal tabanları sanal işlevleri geçersiz kılar vtordisp alanları sunulur.  
  
 Bu seçenekler, tüm kaynak dosyaları etkiler. Kullanım [vtordisp](../../preprocessor/vtordisp.md) bastırmak ve sınıfı tarafından sınıfı temelinde vtordisp alanları yeniden etkinleştirmek için.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)