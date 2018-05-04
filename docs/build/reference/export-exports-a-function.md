---
title: -EXPORT (işlevi dışarı aktarır) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ExportFunctions
- /export
dev_langs:
- C++
helpviewer_keywords:
- /EXPORT linker option
- EXPORT linker option
- -EXPORT linker option
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f366b40e8e40e62f67ec45f3e59ad61eb338c427
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="export-exports-a-function"></a>/EXPORT (İşlevi Dışarı Aktarır)
```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek ile böylece diğer programları işlevi çağırabilirsiniz programınızdan işlevi verebilirsiniz. Ayrıca, verileri dışarı aktarabilirsiniz. Dışarı aktarma genellikle DLL'de tanımlanır.  
  
 *GirişAdı* çağıran program tarafından kullanılacak olan işlevi veya veri öğesinin adı aynıdır. `ordinal` 1 ile 65.535 aralığında dışarı tabloya bir dizini belirtir; belirtmezseniz, `ordinal`, bağlantı bir atar. **NONAME** anahtar sözcüğü dışa aktarır işlevi bir sıra yalnızca olmadan bir *GirişAdı*.  
  
 **Veri** anahtar sözcüğü, dışarı aktarılan öğesi bir veri öğesi olduğunu belirtir. İstemci programında veri öğesi kullanılarak bildirilmelidir **extern __declspec(dllimport)**.  
  
 Önerilen Kullanım sırasına göre listelenen tanım, verme için üç yöntem vardır:  
  
1.  [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) kaynak kodu  
  
2.  Bir [dışarı](../../build/reference/exports.md) .def dosyası deyimi  
  
3.  / Export belirtimi bağlantı komutu  
  
 Üçünü aynı programda kullanılabilir. BAĞLANTI dışarı aktarmaları içeren bir program oluşturduğunda, bir .exp dosyası derleme kullanılmadığı sürece ayrıca bir içeri aktarma kitaplığı oluşturur.  
  
 BAĞLANTI kullanır tanımlayıcıların forms donatılmış. .Obj dosya oluşturduğunda, derleyici tanımlayıcı süsler. Varsa *GirişAdı* ve kendi içinde bağlayıcı için belirtilen (kaynak kodunda göründüğü gibi) form, bağlantı denemeleri adı ile eşleşmesi. Benzersiz bir eşleşme bulamazsanız, bağlantı bir hata iletisi gönderir. Kullanım [DUMPBIN](../../build/reference/dumpbin-reference.md) almak için aracı [adlar](../../build/reference/decorated-names.md) form bağlayıcıya belirtmek gerektiğinde bir tanımlayıcı.  
  
> [!NOTE]
>  Bildirilen C tanımlayıcıları düzenlenmiş biçiminde belirtmeyin `__cdecl` veya `__stdcall`.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Seçenek içine türünü **ek seçenekler** kutusu.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)