---
title: /Fe (EXE Dosyasını Adlandır)
ms.date: 11/04/2016
f1_keywords:
- /fe
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
ms.openlocfilehash: 5901ef1997cfea84c97b6d91b30335ff7dbc1d9f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818056"
---
# <a name="fe-name-exe-file"></a>/Fe (EXE Dosyasını Adlandır)

Bir ad ve .exe dosyası veya DLL derleyici tarafından oluşturulan bir dizini belirtir.

## <a name="syntax"></a>Sözdizimi

> **/FE**[_pathname_] **/Fe:** _yol adı_

### <a name="arguments"></a>Arguments

*yol adı*<br/>
Göreli veya mutlak yolunu ve temel dosya adı veya göreli veya mutlak yol bir dizin ya da oluşturulan yürütülebilir dosya için kullanılacak temel dosya adı.

## <a name="remarks"></a>Açıklamalar

**/Fe** seçeneği, çıkış dizini, çıkış yürütülebilir adı veya her ikisi de oluşturulan yürütülebilir dosyanın belirtmenize olanak sağlar. Varsa *pathname* biten bir yol ayırıcı (**&#92;**), yalnızca çıkış dizini belirtmek için kabul edilir. Aksi halde, son bileşeni *pathname* çıkış dosyası taban adı ve geri kalanı kullanılan *pathname* çıktı dizini belirtir. Varsa *pathname* herhangi bir yol ayırıcıları yok. geçerli dizinde çıkış dosyası adını belirtmek için kabul edilir. *Pathname* çift tırnak içine alınmalıdır (**"**), boşluklar gibi kısa bir yol olamaz herhangi bir karakter içeriyorsa, karakter veya yol bileşenleri sekiz karakterden daha uzun uzun genişletilmiş.

Zaman **/Fe** seçeneği belirtilmezse veya bir dosya açıldığında temel adı belirtilmedi *pathname*, derleyici çıktı dosyasının temel belirtilen ilk kaynak ya da nesne dosyası adını kullanarak varsayılan bir ad sağlar. komut satırını ve uzantısı .exe veya .dll üzerinde.

Belirtirseniz [/c (derleme olmadan bağlamayı)](c-compile-without-linking.md) seçeneği **/Fe** hiçbir etkisi olmaz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **bağlayıcı** > **genel** özellik sayfası.

1. Değiştirme **çıkış dosyası** özelliği. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırını derler ve geçerli dizindeki tüm C kaynak dosyalarının bağlar. Elde edilen çalıştırılabilir dosyayı PROCESS.exe adlı ve "C:\Users\User Name\repos\My Project\bin" dizininde oluşturulur.

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>Örnek

Aşağıdaki komut satırı yürütülebilir bir dosyada oluşturur `C:\BIN` geçerli dizin ilk kaynak dosyası olarak aynı temel ada sahip:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)<br/>
