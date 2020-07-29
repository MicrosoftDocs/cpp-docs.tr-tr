---
title: /vd (Yapı Yer Değiştirmelerini Devre Dışı Bırak)
ms.date: 11/04/2016
f1_keywords:
- /vd
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
ms.openlocfilehash: df8891cc71dd5a4cfd417969578c0c1b46ae3be3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223817"
---
# <a name="vd-disable-construction-displacements"></a>/vd (Yapı Yer Değiştirmelerini Devre Dışı Bırak)

## <a name="syntax"></a>Söz dizimi

```
/vdn
```

## <a name="arguments"></a>Bağımsız değişkenler

**0**<br/>
Vtordisp Oluşturucusu/yıkıcı değiştirme üyesini bastırır. Yalnızca tüm sınıf oluşturucularının ve yıkıcılarının sanal işlevleri neredeyse çağırdıklarından eminseniz bu seçeneği belirleyin.

**1**<br/>
Gizli vtordisp Oluşturucusu/yıkıcı değiştirme üyelerinin oluşturulmasına izin vermez. Bu seçenek varsayılandır.

**2**<br/>
Oluşturulan bir nesne üzerinde [dynamic_cast işlecini](../../cpp/dynamic-cast-operator.md) kullanmanıza olanak sağlar. Örneğin, bir sanal taban sınıftan türetilmiş bir sınıfa bir dynamic_cast.

**/VD2** sanal işlevleri olan sanal bir tabanınız olduğunda bir vtordisp alanı ekler. **/vd1** yeterli olmalıdır. **/VD2** gerekli olduğu en yaygın durum, sanal tabandaki tek sanal işlevin yıkıcıdır.

## <a name="remarks"></a>Açıklamalar

Bu seçenekler yalnızca sanal esaları kullanan C++ kodu için geçerlidir.

Visual C++, sanal devralmanın kullanıldığı durumlarda C++ oluşturma yer değiştirme desteğini uygular. Oluşturma sorunları, bir sanal tabanında bildirildiği ve türetilmiş bir sınıfta geçersiz kılınan bir sanal işlev, daha fazla türetilmiş bir sınıfın oluşturulması sırasında bir oluşturucudan çağrıldığında oluşturulan sorunu çözüyor.

Bu sorun, sanal işleve, **`this`** bir sınıfın sanal tabanlarının ve türetilmiş sınıflarının yerini alan farklılıkları arasındaki uyuşmazlıklara neden olarak geçirilebileceği için hatalı bir işaretçiye yol açabilir. Çözüm, bir sınıfın her bir sanal tabanı için vtordisp alanı olarak adlandırılan tek bir yapı öteleme ayarı sağlar.

Varsayılan olarak, vtordisp alanları, kod Kullanıcı tanımlı oluşturucular ve yıkıcıları her tanımlıyorsa ve ayrıca sanal temellerin sanal işlevlerini geçersiz kıldığında ortaya çıkartılır.

Bu seçenekler tüm kaynak dosyaları etkiler. Bir sınıf temelinde vtordisp alanlarını bastırmak ve sonra yeniden etkinleştirmek için [vtordisp](../../preprocessor/vtordisp.md) kullanın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
