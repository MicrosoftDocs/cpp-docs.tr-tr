---
title: -Fe (EXE dosyasını Adlandır) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fe
dev_langs:
- C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0afd8a863c9b8482e2b7f3868047845818bd2923
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377063"
---
# <a name="fe-name-exe-file"></a>/Fe (EXE Dosyasını Adlandır)

Bir adı ve DLL derleyici tarafından oluşturulan ve .exe dosyası için bir dizini belirtir.

## <a name="syntax"></a>Sözdizimi

> **/FE**[_pathname_]  
> **/ UD:** _yol adı_  

### <a name="arguments"></a>Arguments

*yol adı*<br/>
Göreli veya mutlak bir yol ve temel dosya adı veya göreli veya mutlak bir yol bir dizin ya da oluşturulan yürütülebilir dosyası kullanmak için temel dosya adı.

## <a name="remarks"></a>Açıklamalar

**/Fe** seçeneği çıktı dizini, çıktı yürütülebilir dosya adı veya her ikisi de oluşturulan yürütülebilir dosyanın belirtmenize olanak verir. Varsa *pathname* yol ayırıcı sona erer (**&#92;**), yalnızca belirtilen çıkış dizinine belirtmek için kabul edilir. Aksi halde, son bileşeni *pathname* çıktı dosyasını temel ad ve geri kalan kullanılan *pathname* çıkış dizinini belirtir. Varsa *pathname* herhangi yol ayırıcıları yok geçerli dizinde çıktı dosyası adını belirtmek için kabul edilir. *Pathname* çift tırnak içine alınmalıdır (**"**), boşluk gibi kısa bir yol olamaz. herhangi bir karakteri içeriyorsa karakter veya yol bileşenlerini sekiz karakterden daha uzun genişletilmiş.

Zaman **/Fe** seçeneği belirtilmezse ya da bir dosya açıldığında temel adı belirtilen değil *pathname*, derleyici çıktı dosyası belirtilen ilk kaynak ya da nesne dosyasının temel adını kullanarak varsayılan adı sağlar. komut satırı ve uzantısı .exe veya .dll.

Belirtirseniz [/c (derleme olmadan bağlama)](c-compile-without-linking.md) seçeneği **/Fe** hiçbir etkisi olmaz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **bağlayıcı** > **genel** özellik sayfası.

1. Değiştirme **çıktı dosyası** özelliği. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını derler ve geçerli dizindeki tüm C kaynak dosyaları bağlar. Sonuçta elde edilen yürütülebilir dosyasını PROCESS.exe olarak adlandırılır ve "C:\Users\User Name\repos\My Project\bin" dizininde oluşturulur.

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>Örnek

Aşağıdaki komut satırı yürütülebilir bir dosya oluşturur `C:\BIN` geçerli dizinin ilk kaynak dosya olarak aynı temel adla:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](../../build/reference/output-file-f-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)<br/>
