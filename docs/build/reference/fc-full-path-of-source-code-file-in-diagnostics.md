---
title: /FC (Kaynak Kodu Dosyasının Tanılamadaki Tam Yolu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
ms.openlocfilehash: 3629ec35f0be5ebfd384b949acb2910dcbea3318
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624919"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (Kaynak Kodu Dosyasının Tanılamadaki Tam Yolu)

Derleyici tanılama geçirilen kaynak kodu dosyalarının tam yolu görüntülemek derleyicinin neden olur.

## <a name="syntax"></a>Sözdizimi

> /FC

## <a name="remarks"></a>Açıklamalar

Aşağıdaki kod örneği göz önünde bulundurun:

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

Olmadan **/FC**, tanılama metin tanılama şu metne benzer olacaktır:

- compiler_option_FC.cpp(5): hatası C2143: söz dizimi hatası: eksik ';' önce '}'

İle **/FC**, tanılama metin tanılama şu metne benzer olacaktır:

- c:\test\compiler_option_fc.cpp(5): hatası C2143: söz dizimi hatası: eksik ';' önce '}'

**/FC** kullanırken bir dosya adı tam yolunu görmek isterseniz de gerekli &#95; &#95;dosya&#95; &#95; makrosu. Bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md) hakkında daha fazla bilgi için &#95; &#95;dosya&#95;&#95;.

**/FC** seçeneği tarafından kapsanıyor **/zi**. Hakkında daha fazla bilgi için **/zi**, bkz: [/z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md).

**/FC** küçük tam yollarını çıkarır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **Gelişmiş** özellik sayfası.

1. Değiştirme **tam yolları kullan** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)
