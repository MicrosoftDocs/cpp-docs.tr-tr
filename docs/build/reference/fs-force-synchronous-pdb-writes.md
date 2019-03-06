---
title: /FS (Zaman Uyumlu PDB Yazmalarını Zorla)
ms.date: 11/04/2016
f1_keywords:
- /FS
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
ms.openlocfilehash: 87bdb98b57fa6458b25aef32f81e2c28cf4f8bb5
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422535"
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (Zaman Uyumlu PDB Yazmalarını Zorla)

Zorlar, program veritabanı (PDB) dosyasına yazar — tarafından oluşturulan [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) veya [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)— MSPDBSRV seri hale. EXE.

## <a name="syntax"></a>Sözdizimi

```
/FS
```

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, zaman **/zi** veya **/zi** belirtilirse, derleyicinin tür bilgisini ve sembolik hata ayıklama bilgisini yazmak için PDB dosyalarını kilitler. Bu, derleyicinin türleri sayısı büyük olduğunda tür bilgisi üretmek için gereken süreyi önemli ölçüde azaltabilir. Başka bir işlem PDB dosyası geçici olarak kilitler, — örneğin, virüsten koruma programı — derleyici tarafından yazma işlemleri başarısız olabilir ve önemli bir hata oluşabilir. Cl.exe birden çok kopyasını aynı PDB dosyası eriştiğinizde de bu sorun oluşabilir; Örneğin, bağımsız bir çözümünüz varsa aynı kullanan projeler Ara dizin veya çıkış dizinleri ve paralel yapılar etkinleştirilir. **/FS** derleyici seçeneği derleyici PDB dosyası kilitlemelerini engeller ve MSPDBSRV gitmek için yazma zorlar. EXE erişim serileştirir. Bu derlemeler önemli ölçüde uzun yapabilir ve birden çok cl.exe aynı anda PDB dosyası erişirken oluşabilecek tüm hatalar engellemez. Böylece Ara ayırmak bağımsız projeler yazma ve çıktı konumlarını ya da olun projelerden biri diğerine bağımlı serileştirilmiş zorla proje derlemeleri çözümünüzü değiştirmenizi öneririz.

[/MP](../../build/reference/mp-build-with-multiple-processes.md) seçeneğini etkinleştirir **/FS** varsayılan olarak.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **C/C++** klasör.

1. Seçin **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik `/FS` seçip **Tamam**.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
