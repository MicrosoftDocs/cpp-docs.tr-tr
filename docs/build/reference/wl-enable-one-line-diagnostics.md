---
title: "-WL (tek satır tanılamayı etkinleştir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /wl
dev_langs: C++
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 48ba6ab05ac596c98c4fa5a95971735c62267a35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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