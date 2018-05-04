---
title: İçeri aktarma kitaplığı ve dışarı aktarma dosyası derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
dev_langs:
- C++
helpviewer_keywords:
- OUT library manager option
- INCLUDE library manager option
- /DEF library manager option
- exporting data
- import libraries, building
- -INCLUDE library manager option
- /OUT library manager option
- DEF library manager option
- -DEF library manager option
- -OUT library manager option
- /INCLUDE library manager option
- -EXPORT library manager option
- exporting data, export (.exp) files
- /EXPORT library manager option
- EXPORT library manager option
- .lib files
- EXP files
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93f817aadf2de826c628a14255ae9257be2f29ba
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="building-an-import-library-and-export-file"></a>İçeri Aktarma Kitaplığı ve Dışarı Aktarma Dosyası Derleme
Derleme içeri aktarma kitaplığı ve dışarı aktarmak için aşağıdaki sözdizimini kullanın:  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 / Def belirtildiğinde, LIB çıktı dosyaları LIB komutunda geçirilen verme belirtimleri oluşturur. Önerilen Kullanım sırasına göre listelenen dışarı aktarmaları belirtme için üç yöntem vardır:  
  
1.  A **__declspec(dllexport)** birini tanımında *objfiles* veya *kitaplıkları*  
  
2.  / Export belirtimi:*adı* LIB komut satırında  
  
3.  Bir açıklamasında bir **dışarı** deyiminde bir `deffile`  
  
 Bunlar, dışarı verme program bağlarken belirtmek için kullanın, aynı yöntemleridir. Bir program birden fazla yöntemini kullanabilirsiniz. LIB komutu bölümlerini belirtebilirsiniz (birden çok gibi *objfiles* ya da/Export belirtimleri) LIB komutu bir komut dosyasında yalnızca yapabileceğiniz bir bağlantı komutu.  
  
 Aşağıdaki seçenekler, içeri aktarma kitaplığı oluşturmaya dairdir ve dışarı aktarmak:  
  
 / ÇIKIŞI: *alma*  
 Varsayılan çıkış dosyası adı için geçersiz kılar *alma* kitaplığı oluşturuluyor. /OUT belirtilmediğinde, varsayılan adı temel ilk nesne dosyası veya LIB komut ve uzantı kitaplıkta adıdır. lib. Dışa aktarma dosyası içeri aktarma kitaplığı ve uzantı aynı temel adı verilir. exp.  
  
 / EXPORT: *GirişAdı*[= *InternalName*] [, @ `ordinal`[, **NONAME**]] [, **veri**]  
 Bir işlevi çağırmak için diğer programları izin vermek için programınızdan işlevi dışarı aktarır. Verileri dışarı aktarabilirsiniz (kullanarak **veri** anahtar sözcüğü). Dışarı aktarma genellikle DLL'de tanımlanır.  
  
 *GirişAdı* çağıran program tarafından kullanılacak olan işlevi veya veri öğesinin adı aynıdır. İsteğe bağlı olarak, belirtebilirsiniz *InternalName* tanımlama program; varsayılan olarak, bilinen işlevi olarak *InternalName* aynı *GirişAdı*. `ordinal` Belirtmezseniz, 1 ile 65.535; aralığında verme tabloya bir dizini belirtir `ordinal`, LIB bir atar. **NONAME** anahtar sözcüğü dışa aktarır işlevi bir sıra yalnızca olmadan bir *GirişAdı*. **Veri** anahtar sözcüğü yalnızca veri nesneleri dışarı aktarmak için kullanılır.  
  
 / INCLUDE: `symbol`  
 Belirtilen simgeyi sembol tablosuna ekler. Bu seçenek, aksi takdirde dahil olmayacaktır bir kitaplık nesnesi kullanılmasını zorlamak için yararlıdır.  
  
 .dll oluşturmadan önce ilk adım, içeri aktarma kitaplığını oluşturursanız, içeri aktarma kitaplığını oluştururken geçirilen gibi aynı nesne dosyaları kümesini .dll oluştururken geçmesi gerektiğini unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma](../../build/reference/working-with-import-libraries-and-export-files.md)