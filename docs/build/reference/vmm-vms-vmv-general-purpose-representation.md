---
title: -vmm, - vms, - vmv (genel amaçlı temsil) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /vms
- /vmm
- /vmv
dev_langs:
- C++
helpviewer_keywords:
- Virtual Inheritance compiler option
- general purpose representation compiler options
- vms compiler option [C++]
- vmm compiler option [C++]
- /vmm compiler option [C++]
- -vmm compiler option [C++]
- -vms compiler option [C++]
- /vms compiler option [C++]
- vmv compiler option [C++]
- /vmv compiler option [C++]
- Single Inheritance compiler option
- -vmv compiler option [C++]
ms.assetid: 0fcd7ae0-3031-4c62-a2a8-e154c8685dae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dd2f79238c890d43678332203acbe9d935a54102
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379568"
---
# <a name="vmm-vms-vmv-general-purpose-representation"></a>/vmm, /vms, /vmv (Genel Amaçlı Temsil)
Kullanılabilir [/vmb, / vmg (temsil yöntemi)](../../build/reference/vmb-vmg-representation-method.md) olarak seçilen [temsil yöntemi](../../build/reference/vmb-vmg-representation-method.md). Bu seçenekler henüz karşılaştı sınıf tanımının devralma modeli belirtin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/vmm  
/vms  
/vmv  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Seçenekler aşağıdaki tabloda açıklanmıştır.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**/vmm**|Birden çok devralma kullandığı için bir sınıf üyesi için bir işaretçi en genel gösterimi belirtir.<br /><br /> Karşılık gelen [devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişkeni [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) olan **birden çok devralma**.<br /><br /> Bu gösterim tek devralma için gereken daha büyük.<br /><br /> Devralma modeli üyesi için bir işaretçi bildirilmedi sınıf tanımı sanal ise derleyici bir hata oluşturur.|  
|**/ VMs**|Hiçbir devralma veya tek devralma kullandığı için bir sınıf üyesi için bir işaretçi en genel gösterimi belirtir.<br /><br /> Karşılık gelen [devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişkeni [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) olan **single_inheritance**.<br /><br /> Bu sınıf üyesi için bir işaretçi en küçük olası gösterimidir.<br /><br /> Üye için bir işaretçi olarak bildirilen bir sınıf tanımı devralma modelinin birden çok ise veya sanal derleyici bir hata oluşturur.|  
|**/vmv**|Sanal devralma kullandığı için bir sınıf üyesi için bir işaretçi en genel gösterimi belirtir. Hiçbir zaman bir hataya neden olur ve varsayılandır.<br /><br /> Karşılık gelen [devralma anahtar sözcüğü](../../cpp/inheritance-keywords.md) ve bağımsız değişkeni [#pragma pointers_to_members](../../preprocessor/pointers-to-members.md) olan **virtual_inheritance**.<br /><br /> Bu seçenek büyük işaretçi ve diğer seçenekleri işaretçiden yorumlamak için ek kod gerektirir.|  
  
 Bu devralma modeli seçeneklerden birini belirttiğinizde, bu model tüm devralma tipine veya işaretçinin önce veya bildirilmiş sınıfı sonra bağımsız olarak sınıfı üyeleri işaretçileri için kullanılır. Tek devralma sınıflar her zaman kullanırsanız, bu nedenle, kod boyutu ile derleme tarafından azaltabilir **/VMs**; ancak, en genel durum (ödün verme pahasına en büyük veri temsili) kullanmak istiyorsanız, ilederleme **/vmv**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ vmb, / vmg (temsil yöntemi)](../../build/reference/vmb-vmg-representation-method.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)