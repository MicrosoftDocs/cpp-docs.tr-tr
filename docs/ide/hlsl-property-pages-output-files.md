---
title: 'HLSL özellik sayfaları: Çıktı dosyaları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
dev_langs:
- C++
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ccd140a1e132cc260c47b00365e03c32acf5cdf
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721593"
---
# <a name="hlsl-property-pages-output-files"></a>HLSL Özellik Sayfaları: Çıktı Dosyaları
HLSL derleyicisi (fxc.exe) aşağıdaki özellikleri yapılandırmak için kullanın, **Çıkış dosyalarını** özelliği. Nasıl erişileceği hakkında daha fazla bilgi için **Çıkış dosyalarını** HLSL klasöründe, özellik sayfasında bakın [Working with Project Properties](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>UIElement Listesi  
- **Üst bilgi değişken adı**

   Kodlanmış HLSL nesne kodu için kullanılan bir dizi adını belirtir. Dizi, HLSL derleyici tarafından çıktı bir üstbilgi dosyasında yer alır. Üst bilgi dosyasının adı tarafından belirtilen **üst bilgi dosyası adını** özelliği.  
  
 Bu özellik için karşılık gelen **/Vn [ad]** komut satırı bağımsız değişkeni.  
  
- **Üst bilgi dosyası adı**

   HLSL derleyicisi tarafından çıkış üst bilgi dosyasının adını belirtir. Üstbilgi bir diziye kodlanmış HLSL nesne kodu içerir. Dizi adı tarafından belirtilen **üst bilgi değişken adı** özelliği.  
  
 Bu özellik için karşılık gelen **/Fh [ad]** komut satırı bağımsız değişkeni.  
  
- **Nesne dosyası adı**

   HLSL derleyicisi tarafından çıktı nesne dosyası adını belirtir. Varsayılan değer olan **$(OutDir) % (Filename) .cso**.  
  
 Bu özellik için karşılık gelen **/Fo [ad]** komut satırı bağımsız değişkeni.  
  
- **Assembler çıkışı**

   **Sadece bütünleştirilmiş kodların listesi (/ Fc)** yalnızca derleme dili ifadelerini çıkarmak için. **Derleme kodu ve onaltılık (/ Fx)** derleme dili ifadelerini hem karşılık gelen işlem kodu onaltılık çıkış. Varsayılan olarak, hiçbir çıkış listedir.  
  
- **Assembler çıkış dosyası**

   HLSL derleyicisi tarafından çıktı derleme listeleme dosyası adını belirtir.  
  
   Bu özellik için karşılık gelen **/Fc [name]** ve **/Fx [name]** komut satırı bağımsız değişkenleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HLSL özellik sayfaları](../ide/hlsl-property-pages.md)   
 [HLSL özellik sayfaları: Genel](../ide/hlsl-property-pages-general.md)   
 [HLSL Özellik Sayfaları: Gelişmiş](../ide/hlsl-property-pages-advanced.md)