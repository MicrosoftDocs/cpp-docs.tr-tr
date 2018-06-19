---
title: -GR (çalışma zamanı türü bilgileri etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
dev_langs:
- C++
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79e91f11fa6397d2ba8279998726249182c541d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374989"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Çalışma Zamanı Türü Bilgileri Etkinleştir)
Çalışma zamanında nesne türlerini denetlemek için kod ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GR[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman **/GR** açıktır, derleyici tanımlar `_CPPRTTI` önişlemci makrosu. Varsayılan olarak, **/GR** açıktır. **/gr-** çalışma zamanı türü bilgileri devre dışı bırakır.  
  
 Kullanım **/GR** derleyici kodunuzda nesne türünü statik olarak çözemezseniz. Genellikle gerek **/GR** seçeneği kodunuzu kullandığında [dynamic_cast işleci](../../cpp/dynamic-cast-operator.md) veya [TypeID](../../cpp/typeid-operator.md). Ancak, **/GR** görüntünüzü .rdata bölümlerini boyutu artar. Kodunuzu kullanmıyorsa **dynamic_cast** veya **TypeID**, **/GR-** daha küçük bir resim üretebilir.  
  
 Çalışma zamanı tür denetimi hakkında daha fazla bilgi için bkz: [çalışma zamanı türü bilgileri](../../cpp/run-time-type-information.md) içinde *C++ dil başvurusu*.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **dil** özellik sayfası.  
  
4.  Değiştirme **çalışma zamanı türü bilgileri etkinleştir** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)