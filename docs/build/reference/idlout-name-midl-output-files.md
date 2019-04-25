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
ms.openlocfilehash: 3816bb85cb3c711075e3fefeec2d706c2f8cc2ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291582"
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

MIDL derleyicisi olan projelerin bağlarken MSVC bağlayıcı tarafından çağrılır [Modülü](../../windows/module-cpp.md) özniteliği.

/ IDLOUT ayrıca MIDL derleyicisi ile ilişkili diğer çıktı dosyalarının dosya adlarını belirtir:

- *filename*.tlb

- *filename*_p.c

- *filename*_i.c

- *filename*.h

*filename*  /ıdlout için geçirdiğiniz parametredir. Varsa [/tlbout](tlbout-name-dot-tlb-file.md) belirtilirse, .tlb dosyasının adını / tlbout alacak *filename*.

/ Idlout ne/tlbout belirtirseniz, bağlayıcı vc70.tlb, vc70.idl vc70_p.c vc70_i.c ve vc70.h oluşturun.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **katıştırılmış IDL** özellik sayfası.

1. Değiştirme **birleştirme IDL taban dosyası adı** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)<br/>
[/IGNOREIDL (Öznitelikleri MIDL'ye İşleme)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)](midl-specify-midl-command-line-options.md)<br/>
[Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)
