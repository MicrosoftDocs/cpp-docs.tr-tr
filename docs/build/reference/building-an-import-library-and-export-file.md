---
description: 'Hakkında daha fazla bilgi edinin: Içeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturma'
title: İçeri Aktarma Kitaplığı ve Dışarı Aktarma Dosyası Derleme
ms.date: 09/05/2018
f1_keywords:
- VC.Project.VCLibrarianTool.ModuleDefinitionFile
- VC.Project.VCLibrarianTool.ExportNamedFunctions
- VC.Project.VCLibrarianTool.GenerateDebug
- VC.Project.VCLibrarianTool.ForceSymbolReferences
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
ms.openlocfilehash: 8fbd06ce06d77721e64294b88632933b3ad71a03
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179518"
---
# <a name="building-an-import-library-and-export-file"></a>İçeri Aktarma Kitaplığı ve Dışarı Aktarma Dosyası Derleme

İçeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturmak için aşağıdaki sözdizimini kullanın:

> **LIB/DEF**[**:**<em>deffile</em>] [*Seçenekler*] [*objfiles*] [*Kitaplıklar*]

/DEF belirtildiğinde, LIB LıB komutuna geçirilen dışa aktarma belirtimlerinden çıkış dosyalarını oluşturur. ' Nin önerilen kullanım sırasıyla listelenen dışarı aktarmaları belirtmek için üç yöntem vardır:

1. **`__declspec(dllexport)`** *Objfiles* veya *kitaplıklarından* birindeki bir tanım

1. LIB komut satırındaki/EXPORT:*Name* belirtimi

1. Bir *deffile* Içindeki **dışarı aktarmalar** deyimindeki bir tanım

Bunlar dışa aktarma programı bağlarken dışarı aktarmaları belirtmek için kullandığınız metodlardır. Bir program birden fazla yöntem kullanabilir. LIB komutunda bir komut dosyasında (örneğin, birden çok *objfiles* veya/Export belirtimleri), TıPKı bir bağlantı komutunda yapabildiğiniz gıbı, lib komutunun parçalarını belirtebilirsiniz.

İçeri aktarma kitaplığı ve dışarı aktarma dosyası oluşturmak için aşağıdaki seçenekler geçerlidir:

> **/Out:** *import*

Oluşturulan *içeri aktarma* kitaplığı için varsayılan çıkış dosyası adını geçersiz kılar. /OUT belirtilmediğinde, varsayılan ad LıB komutunda ve. lib uzantısının ilk nesne dosyasının veya kitaplığının temel adıdır. Dışarı aktarma dosyasına içeri aktarma kitaplığıyla ve. exp uzantısıyla aynı temel ad verilir.

> **/Export:** *EntryName* \[ **=** *InternalName*] \[ , **\@** <em>Ordinal</em> \[ , **noname**]] \[ , **veri**]

Diğer programların işlevi çağırmasını sağlamak için programınızdaki bir işlevi dışarı aktarır. Ayrıca, verileri dışarı aktarabilirsiniz ( **Data** anahtar sözcüğünü kullanarak). Dışarı aktarmalar genellikle DLL 'de tanımlanmıştır.

*EntryName* , çağıran program tarafından kullanılacak şekilde işlevin veya veri öğesinin adıdır. İsteğe bağlı olarak, *InternalName* 'i tanımlama programında bilinen işlev olarak belirtebilirsiniz; Varsayılan olarak, *InternalName* , *EntryName* ile aynıdır. *Ordinal* , 1 ile 65.535 arasında dışa aktarma tablosuna bir dizin belirtir; *sıra* belirtmezseniz, LIB bir tane atar. **Noname** anahtar sözcüğü, *EntryName* olmadan işlevi yalnızca sıra olarak dışa aktarır. **Data** anahtar sözcüğü yalnızca veri nesneleri dışarı aktarmak için kullanılır.

> **/Include:** *simge*

Belirtilen *sembolü* sembol tablosuna ekler. Bu seçenek, başka türlü dahil olmayan bir kitaplık nesnesinin kullanımını zorlamak için yararlıdır.

İçeri aktarma kitaplığınızı bir ön adımda oluşturursanız,. dll 'nizi oluşturmadan önce, içeri aktarma kitaplığını oluştururken geçirdiğiniz gibi,. dll dosyasını oluştururken aynı nesne dosyaları kümesini geçirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Içeri aktarma kitaplıkları ve dışarı aktarma dosyalarıyla çalışma](working-with-import-libraries-and-export-files.md)
