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
ms.openlocfilehash: f0bd8f3a96555cc29d06f74fb44a73bbed32889b
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825584"
---
# <a name="fe-name-exe-file"></a>/Fe (EXE Dosyasını Adlandır)

Derleyici tarafından oluşturulan. exe dosyası veya DLL için bir ad ve dizin belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Fe**[_yol adı_] \
> **/Fe:** _yol adı_

### <a name="arguments"></a>Bağımsız Değişkenler

*PathName*<br/>
Göreli veya mutlak yol ve temel dosya adı ya da bir dizinin göreli ya da mutlak yolu ya da oluşturulan yürütülebilir dosya için kullanılacak taban dosya adı.

## <a name="remarks"></a>Açıklamalar

**/Fe** seçeneği, oluşturulan yürütülebilir dosya için çıkış dizinini, çıkış yürütülebilir adını veya her ikisini belirtmenizi sağlar. Yol *adı* bir yol ayırıcısıyla (**&#92;**) sonlanıyorsa, yalnızca çıkış dizinini belirtmek kabul edilir. Aksi takdirde, *yol adının* son bileşeni çıkış dosyası temel adı olarak kullanılır ve geri kalan *yol* , çıkış dizinini belirtir. Yol *adının* herhangi bir yol ayırıcısı yoksa, geçerli dizinde çıkış dosyası adının belirtilmesi varsayılır. Boşluk, genişletilmiş karakterler veya sekiz karakterden uzun yol bileşenleri gibi kısa bir yolda yer alan bir karakter içeriyorsa, *yol adı* çift tırnak (**"**) içine alınmalıdır.

**/Fe** seçeneği belirtilmediğinde veya *PathName*öğesinde bir dosya taban adı belirtilmediğinde, derleyici çıkış dosyasına komut satırında belirtilen ilk kaynak veya nesne dosyasının temel adını ve. exe veya. dll uzantısını kullanarak varsayılan bir ad verir.

[/C (bağlama olmadan Derle)](c-compile-without-linking.md) seçeneğini belirtirseniz, **/Fe** hiçbir etkiye sahip değildir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **Bağlayıcısı** > **genel** özellik sayfasını açın.

1. **Çıkış dosyası** özelliğini değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.

## <a name="example"></a>Örnek

Aşağıdaki komut satırı, geçerli dizindeki tüm C kaynak dosyalarını derler ve bağlar. Elde edilen yürütülebilir dosya, PROCESS. exe olarak adlandırılır ve "C:\Users\User \ Kullanıcı adı" dizininde oluşturulur.

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>Örnek

Aşağıdaki komut satırı, geçerli dizindeki ilk kaynak dosyayla `C:\BIN` aynı temel adı taşıyan bir yürütülebilir dosya oluşturur:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Yol adını belirtme](specifying-the-pathname.md)<br/>
