---
title: -WL (tek satır tanılamayı etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /wl
dev_langs:
- C++
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e82a3273673d45d1abf3ac201d7a0f63334cecbb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718678"
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

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)