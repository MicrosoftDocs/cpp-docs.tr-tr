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
ms.openlocfilehash: 58a6b41e66f7ec37ad02747edb8331049b9baef5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376793"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (Tek Satır Tanılamayı Etkinleştir)
Ek bilgi için bir hata veya uyarı iletisi ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/WL  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ve uyarı iletileri C++ derleyicisi tarafından görüntülenen, varsayılan olarak, yeni bir satıra ek bilgi izlenebilir. Komut satırından derlerken bilgilerinin ek satırı hata veya uyarı iletisi eklenmiş. Bir günlük dosyasına, yapı çıktı yakalamak ve tüm hataları ve Uyarıları bulmak için günlük işlem varsa bu arzu olabilir. Noktalı virgül hata veya uyarı iletisi ek satırından ayırın.  
  
 Tüm hata ve uyarı iletileri bilgilerinin ek bir satır var. Aşağıdaki kod, ek bir bilgi bulunur hataya neden olur; kullandığınızda test etme olanak sağlayacak **/WL**.  
  
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
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)