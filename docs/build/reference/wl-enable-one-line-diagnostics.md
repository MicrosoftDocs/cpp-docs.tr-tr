---
title: /WL (Tek Satır Tanılamayı Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- /wl
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
ms.openlocfilehash: c0d5110615f66dcf4f7dc170d89ee58c2e8fa5cb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811985"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (Tek Satır Tanılamayı Etkinleştir)

Ek bilgi için bir hata veya uyarı iletisi ekler.

## <a name="syntax"></a>Sözdizimi

```
/WL
```

## <a name="remarks"></a>Açıklamalar

Hata ve uyarı iletilerini C++ derleyicisinden görüntülenen varsayılan olarak yeni bir satıra ek bilgileri tarafından izlenebilir. Komut satırından derlerken hata veya uyarı iletisi için ek bilgi satırının eklenebilecek. Bir günlük dosyası için derleme çıkışınızı yakalamak ve ardından tüm hataları ve Uyarıları bulmak için günlük işlem bu uygun olabilir. Noktalı virgül hata veya uyarı iletisi ek satırından ayırın.

Tüm hata ve uyarı iletilerini bilgilerin ek bir satır vardır. Aşağıdaki kod, ek bir bilgi satırı olan bir hata oluşturur; özelliğini kullandığınızda uygulamanın etkisini sınayın olanak tanıyan **/WL**.

```
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
