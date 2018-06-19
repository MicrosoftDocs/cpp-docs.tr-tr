---
title: -hotpatch (düzeltme eki eklenebilen görüntü oluşturma) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- C++
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb0f27c8da03104ee3633d9ea1a5f1232407931e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376211"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Düzeltme Eki Eklenebilen Görüntü Oluşturma)
Bir görüntü anında düzeltme için hazırlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/hotpatch  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman **/hotpatch** kullanılan bir derlemede derleyici ilk yönerge her işlevi en az iki bayt anında düzeltme için gerekli olduğu olmasını sağlar.  
  
 Kullandıktan sonra bir görüntü düzeltme eki eklenebilen, yapmak için hazırlık tamamlamak için **/hotpatch** derlemek için kullanmanız gerekir [/FUNCTIONPADMIN (düzeltme eki eklenebilen görüntü oluşturma)](../../build/reference/functionpadmin-create-hotpatchable-image.md) bağlamak için. Derleme ve görüntünün cl.exe, yönelik bir çağrı kullanılarak bağlantı **/hotpatch** gelir **/functionpadmin**.  
  
 Yönergeleri her zaman iki bayt olduğundan veya büyük ARM mimarisi, temel ve çünkü derleme her zaman kabul x64 gibi **/hotpatch** belirtildiyse, belirtmek zorunda değilsiniz **/hotpatch** zaman Bu hedefler için derleme; Ancak, yine kullanarak bağlanmalıdır **/functionpadmin** kendileri için düzeltme eki eklenebilen görüntü oluşturmak için. **/Hotpatch** derleyici seçeneği yalnızca etkiler x86 derleme.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği eklemek **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="guidance"></a>Kılavuz  
 Güncelleştirme yönetimi hakkında daha fazla bilgi için bkz: "Güncelleştirme yönetimi için Güvenlik Kılavuzu" [ http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx ](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)