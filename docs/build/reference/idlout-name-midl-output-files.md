---
title: /IDLOUT (MIDL Çıktı Dosyalarını Adlandır)
ms.date: 11/04/2016
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
ms.openlocfilehash: b21e8eb266de9a0baa0512a82acb0ae8a9f650a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500431"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (MIDL Çıktı Dosyalarını Adlandır)

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>Parametreler

*Yolu*<br/>
Bir mutlak veya göreli yol belirtimi. Bir yolu belirterek, yalnızca bir .idl dosyasının konumunu etkiler; diğer tüm dosyaları proje dizininde yer alır.

*Dosya adı*<br/>
MIDL derleyicisi tarafından oluşturulan .idl dosyasının adını belirtir. Dosyanın uzantısı varsayılır; belirtin *filename*.idl uzantı istiyorsanız .idl.

## <a name="remarks"></a>Açıklamalar

/ Idlout seçeneği, .idl dosyasının uzantısını ve adını belirtir.

MIDL derleyicisi olan projelerin bağlanırken Visual C++ bağlayıcı tarafından çağrılır [Modülü](../../windows/module-cpp.md) özniteliği.

/ IDLOUT ayrıca MIDL derleyicisi ile ilişkili diğer çıktı dosyalarının dosya adlarını belirtir:

- *filename*.tlb

- *filename*_p.c

- *filename*_i.c

- *filename*.h

*filename*  /ıdlout için geçirdiğiniz parametredir. Varsa [/tlbout](../../build/reference/tlbout-name-dot-tlb-file.md) belirtilirse, .tlb dosyasının adını / tlbout alacak *filename*.

/ Idlout ne/tlbout belirtirseniz, bağlayıcı vc70.tlb, vc70.idl vc70_p.c vc70_i.c ve vc70.h oluşturun.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **katıştırılmış IDL** özellik sayfası.

1. Değiştirme **birleştirme IDL taban dosyası adı** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[/IGNOREIDL (Öznitelikleri MIDL'ye İşleme)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)](../../build/reference/midl-specify-midl-command-line-options.md)<br/>
[Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)