---
title: Bir içeri aktarma kitaplığını ve dışarı aktarma dosyası derleme | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
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
ms.openlocfilehash: c832ee24d500eba28c14713d1c0a092baf90a440
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894622"
---
# <a name="building-an-import-library-and-export-file"></a>İçeri Aktarma Kitaplığı ve Dışarı Aktarma Dosyası Derleme

İçeri aktarma kitaplığı oluşturmak ve dosyasını dışarı aktarmak için aşağıdaki sözdizimini kullanın:

> **LIB/def**[**:**<em>deffile</em>] [*seçenekleri*] [*objfiles*] [*kitaplıkları*]

/ Def belirtildiğinde LIB çıktı dosyaları LIB komutta geçirilen dışarı aktarma belirtimleri oluşturur. Önerilen Kullanım sırasına göre listelenmiş dışa belirtmek için üç yöntem vardır:

1. A **__declspec(dllexport)** birini tanımında *objfiles* veya *kitaplıkları*

2. / Export belirtimi:*adı* LIB komut satırında

3. Bir tanım bir **dışarı AKTARMALARI** deyiminde bir *deffile*

Bunlar bir dışarı aktarma programı'nı bağlarken dışarı aktarmaları belirtmek için kullandığınız aynı yöntemleridir. Bir program, birden fazla yöntemi kullanabilirsiniz. LIB komutunun bölümleri belirtebilirsiniz (gibi birden çok *objfiles* veya/Export belirtimleri) LIB komutu bir komut dosyasında bıraktığınız gibi için bir bağlantı komutu.

Aşağıdaki seçenekler, içeri aktarma kitaplığı oluşturmaya dairdir ve dosyasını dışa aktarın:

> **/ OUT:** *içeri aktarma*  

İçin varsayılan çıkış dosyası adını geçersiz kılar *alma* kitaplığı oluşturuluyor. / Out belirtilmediğinde, varsayılan adı temel nesne dosyası birinci ya da LIB komut ve uzantı kitaplıkta adıdır. LIB. Dışarı aktarma dosyası içeri aktarma kitaplığını ve uzantı olarak aynı temel adı verilir. üs.

> **/ EXPORT:** *GirişAdı* \[ **=** *InternalName*]\[,**\@** <em>sıralı</em>\[, **NONAME**]]\[, **veri**]

Bir işlev programınızı işlevi çağırmak diğer programları olanak verir. Ayrıca verileri aktarabilirsiniz (kullanarak **veri** anahtar sözcüğü). Dışarı aktarmalar, genellikle bir DLL içinde tanımlanır.

*GirişAdı* çağırma program tarafından kullanılacak olan işlev veya veri öğesinin adını aynıdır. İsteğe bağlı olarak belirtebilirsiniz *InternalName* tanımlama program; varsayılan olarak bilinen işlevi olarak *InternalName* aynı *GirişAdı*. *Sıralı* belirtmezseniz, dizin ' % s'aralık 1 ile 65.535; dışa aktarma tablosunda içine belirtir *sıralı*, LIB bir atar. **NONAME** anahtar sözcüğü işlevin olmadan yalnızca bir sıralı, dışarı bir *GirişAdı*. **Veri** anahtar sözcüğü, yalnızca veri nesneleri dışarı aktarmak için kullanılır.

> **/ INCLUDE:** *simgesi*

Belirtilen ekler *sembol* sembol tablosuna. Bu seçenek, aksi takdirde dahil olmazdı bir kitaplık nesnesi kullanılmasını zorlamak için yararlıdır.

Başlangıç bir adımda, .dll oluşturmadan önce içeri aktarma kitaplığını oluşturursanız, içeri aktarma kitaplığı derlerken geçti olarak, aynı nesne dosyaları kümesini .dll oluştururken geçmesi gerektiğini unutmayın.

## <a name="see-also"></a>Ayrıca Bkz.

[İçeri Aktarma Kitaplıkları ve Dışarı Aktarma Dosyalarıyla Çalışma](../../build/reference/working-with-import-libraries-and-export-files.md)