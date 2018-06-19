---
title: -Zg (işlev prototipleri üret) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zg
dev_langs:
- C++
helpviewer_keywords:
- Zg compiler option [C++]
- /Zg compiler option [C++]
- function prototypes, generate function prototypes compiler option
- -Zg compiler option [C++]
- generate function prototypes compiler option
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8288da0981878b17ad0c2091bf2a45569b51740d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380540"
---
# <a name="zg-generate-function-prototypes"></a>/Zg (İşlev Prototipleri Üret)
Kaldırıldı. Kaynak dosyasında tanımlanan her işlev için işlev prototipi oluşturur, ancak kaynak dosya derlenmiyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Zg  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu derleyici seçeneği artık kullanılamıyor. Visual C++ 2015'te kaldırıldı. Visual C++ eski sürümleri kullanıcılar için bu sayfayı kalır.  
  
 İşlev prototipi işlevi dönüş türü ve bir bağımsız değişken türü listesi içerir. Bağımsız değişken türü listesi biçimsel parametresi işlevin türlerinden oluşturulur. Kaynak dosyanın zaten mevcut herhangi bir işlev prototipleri göz ardı edilir.  
  
 Prototipler listesini standart çıktıya yazılır. Bu liste gerçek bağımsız değişkenler ve biçimsel parametresi bir işlevin uyumlu olduğunu doğrulamak yararlı bulabilirsiniz. Standart çıktıyı bir dosyaya yönlendirerek listesini kaydedebilirsiniz. Kullanabileceğiniz sonra **#include** işlev prototipleri listesi kaynak dosyanızın bir parçası haline getirmek için. Bunun yapılması bağımsız değişken türü denetimi yapmak derleyici neden olur.  
  
 Kullanırsanız **/Zg** seçeneği ve programınız yapısı, enum, veya birleşim türü (veya gibi türler işaretçiler) biçimsel parametresi varsa, her yapısı, numaralandırma veya birleşim türü bildiriminde bir etiket (ad) olmalıdır. Aşağıdaki örnekte, etiket adı olduğu `MyStruct`.  
  
```C  
// Zg_compiler_option.c  
// compile with: /Zg  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```  
  
 **/Zg** seçeneği Visual Studio 2005'te kullanımdan kaldırılmıştır ve Visual Studio 2015'te kaldırılmıştır. Visual C++ derleyicisi C tarzı eski kod için destek kaldırdı. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** içinde [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
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