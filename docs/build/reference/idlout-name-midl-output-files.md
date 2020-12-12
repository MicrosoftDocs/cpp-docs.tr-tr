---
description: Daha fazla bilgi edinin:/ıDLOUT (MıDL çıktı dosyalarını Adlandır)
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
ms.openlocfilehash: 9835721d3e9b376feca51d87d375efa79dc43df7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199850"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (MIDL Çıktı Dosyalarını Adlandır)

```
/IDLOUT:[path\]filename
```

## <a name="parameters"></a>Parametreler

*Yolun*<br/>
Mutlak veya göreli yol belirtimi. Bir yol belirterek, yalnızca bir. IDL dosyasının konumunu etkilersiniz; diğer tüm dosyalar proje dizinine yerleştirilir.

*filename*<br/>
MıDL derleyicisi tarafından oluşturulan. IDL dosyasının adını belirtir. Hiçbir dosya uzantısı varsayıldı; . IDL uzantısı istiyorsanız *filename*. IDL belirtin.

## <a name="remarks"></a>Açıklamalar

/IDLOUT seçeneği,. IDL dosyasının adını ve uzantısını belirtir.

MıDL derleyicisi, [module](../../windows/attributes/module-cpp.md) özniteliği olan projeler bağlanırken MSVC bağlayıcı tarafından çağırılır.

/IDLOUT Ayrıca MıDL derleyicisi ile ilişkili diğer çıkış dosyalarının dosya adlarını belirtir:

- *filename*. tlb

- *filename* _p. c

- *filename* _i. c

- *filename*. h

*filename* ,/ıdlout'e geçirdiğiniz parametredir. [/Tlhakkında](tlbout-name-dot-tlb-file.md) belirtilmişse,. tlb dosyasının adını/TLS *Dosya* adı ile alır.

Ne/ıDLOUT ne de/TLI belirtirseniz, bağlayıcı vc70. tlb, vc70. IDL, vc70_p. c, vc70_i. c ve vc70. h oluşturur.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **KATıŞTıRıLMıŞ IDL** Özellik sayfasına tıklayın.

1. **Merge IDL taban dosya adı** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[/IGNOREıDL (öznitelikleri MıDL 'ye Işleme)](ignoreidl-don-t-process-attributes-into-midl.md)<br/>
[/MıDL (MıDL komut satırı seçeneklerini belirt)](midl-specify-midl-command-line-options.md)<br/>
[Öznitelikli Program Oluşturma](../../windows/attributes/cpp-attributes-com-net.md)
