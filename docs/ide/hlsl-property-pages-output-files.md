---
title: 'HLSL özellik sayfaları: Çıktı dosyaları'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
ms.openlocfilehash: 746781142d9989910f526c85b38516e8d5302ada
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739498"
---
# <a name="hlsl-property-pages-output-files"></a>HLSL özellik sayfaları: Çıktı dosyaları

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

## <a name="see-also"></a>Ayrıca bkz.

[HLSL Özellik Sayfaları](../ide/hlsl-property-pages.md)<br>
[HLSL Özellik Sayfaları: Genel](../ide/hlsl-property-pages-general.md)<br>
[HLSL Özellik Sayfaları: Gelişmiş](../ide/hlsl-property-pages-advanced.md)
