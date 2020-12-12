---
description: Daha fazla bilgi için:/FS (zaman uyumlu PDB yazmaları zorla)
title: /FS (Zaman Uyumlu PDB Yazmalarını Zorla)
ms.date: 11/04/2016
f1_keywords:
- /FS
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
ms.openlocfilehash: 2dcddd046cc7232f40be5a54d73e659ed099e85d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192037"
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (Zaman Uyumlu PDB Yazmalarını Zorla)

MSPDBSRV.EXE aracılığıyla serileştirilmesi için [/Zi](z7-zi-zi-debug-information-format.md) veya [/Zi](z7-zi-zi-debug-information-format.md)tarafından oluşturulan program veritabanı (pdb) dosyasına yazmaları zorlar.

## <a name="syntax"></a>Syntax

```
/FS
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, **/Zi** veya **/Zi** belirtildiğinde, derleyici tür bilgilerini ve simgesel hata ayıklama bilgilerini yazmak için pdb dosyalarını kilitler. Bu, tür sayısı büyük olduğunda derleyicinin tür bilgilerini oluşturma süresini önemli ölçüde azaltabilir. Başka bir işlem PDB dosyasını geçici olarak kilitlerse — Örneğin, bir virüsten koruma programı — derleyici tarafından yazma işlemleri başarısız olabilir ve önemli bir hata oluşabilir. Bu sorun, aynı PDB dosyasına cl.exe birden çok kopyası olduğunda da gerçekleşebilir — Örneğin, çözümünüz aynı ara dizinleri veya çıkış dizinlerini kullanan bağımsız projelere sahipse ve paralel derlemeler etkinse. **/FS** derleyici SEÇENEĞI derleyicinin pdb dosyasını kilitlemesini ve yazma işlemini MSPDBSRV.EXE, erişimi seri hale getirir. Bu, derlemeleri önemli ölçüde daha uzun hale getirir ve cl.exe birden çok örneği aynı anda PDB dosyasına erişilişinde oluşabilecek tüm hataları engellemez. Bağımsız projelerin ayrı ara ve çıkış konumlarına yazmasını veya bir projeden birini, serileştirilmiş proje yapılarını zorlamak için bağımlı hale getirmenizi sağlayacak şekilde çözümünüzü değiştirmenizi öneririz.

[/MP](mp-build-with-multiple-processes.md) seçeneği varsayılan olarak **/FS** 'yi mümkün.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü seçin.

1. **Komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** özelliğini içerecek şekilde değiştirin `/FS` ve ardından **Tamam**' ı seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
