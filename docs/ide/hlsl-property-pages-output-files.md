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
ms.openlocfilehash: 4fd1dc3ba92201567f24aa84ff8dddcd96798b38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="hlsl-property-pages-output-files"></a>HLSL Özellik Sayfaları: Çıktı Dosyaları
HLSL derleyici (fxc.exe) aşağıdaki özellikleri yapılandırmak için kullanın, **çıktı dosyaları** özelliği. Nasıl erişileceği hakkında bilgi için **çıktı dosyaları** özellik sayfası HLSL klasöründeki bkz [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Üstbilgi değişken adı**  
 Kodlanmış HLSL nesne kodu için kullanılan bir dizi adını belirtir. Dizi tarafından HLSL Derleyici çıktısı bir üstbilgi dosyasında yer alır. Tarafından belirtilen üstbilgi dosyası adı **üstbilgi dosyası adı** özelliği.  
  
 Bu özellik karşılık gelen **/Vn [name]** komut satırı bağımsız değişkeni.  
  
 **Üstbilgi dosyası adı**  
 HLSL derleyici tarafından çıktısı üstbilgi dosyası adını belirtir. Üstbilgi bir diziye kodlanmış HLSL nesne kodu içerir. Dizi adı tarafından belirtilen **üstbilgi değişken adı** özelliği.  
  
 Bu özellik karşılık gelen **/Fh [name]** komut satırı bağımsız değişkeni.  
  
 **Nesne dosya adı**  
 HLSL derleyici tarafından çıktı nesne dosya adını belirtir. Varsayılan değer olan **$(OutDir) % (dosya adı) .cso**.  
  
 Bu özellik karşılık gelen **/Fo [name]** komut satırı bağımsız değişkeni.  
  
 **Derleyici çıktı**  
 **Yalnızca derleme listeleme (/ Fc)** yalnızca derleme dili ifadeleri çıktısını almak için. **Derleme kodunu ve onaltılık (/ Fx)** assembly dili ifadeleri ve karşılık gelen işlem kodu onaltılık çıkış için. Varsayılan olarak, hiçbir çıkış listedir.  
  
 **Derleyici çıktı dosyası**  
 HLSL derleyici tarafından çıktı derleme listeleme dosya adını belirtir.  
  
 Bu özellik karşılık gelen **/Fc [name]** ve **/Fx [name]** komut satırı bağımsız değişkenleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [HLSL özellik sayfaları](../ide/hlsl-property-pages.md)   
 [HLSL özellik sayfaları: Genel](../ide/hlsl-property-pages-general.md)   
 [HLSL Özellik Sayfaları: Gelişmiş](../ide/hlsl-property-pages-advanced.md)