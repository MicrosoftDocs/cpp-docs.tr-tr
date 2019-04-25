---
title: dllexport ve dllimport ile Satır İçin C İşlevlerini Tanımlama
ms.date: 11/04/2016
helpviewer_keywords:
- inline functions [C++], with dllexport and dllimport
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
- dllexport attribute [C++]
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
ms.openlocfilehash: 2e43f01b495a03e4f50295de42afa9b6c6b38173
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234424"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>dllexport ve dllimport ile Satır İçin C İşlevlerini Tanımlama

**Microsoft'a özgü**

`dllexport` özniteliğiyle bir işlevi satır içi olarak tanımlayabilirsiniz. Bu durumda, programdaki herhangi bir modülün işleve başvurup başvurmadığına bakılmaksızın işlevin her zaman örneği oluşturulur ve işlev dışarı aktarılır. İşlevin, başka bir program tarafından içeri aktarıldığı varsayılır.

Bildirilen bir işlevi de satır içi olarak tanımlayabilirsiniz **dllimport** özniteliği. Bu durumda, işlev Genişletilebilir (/Ob (satır içi) derleyici seçeneği belirtimi tabidir) ancak hiçbir zaman örneği. Özellikle, satır içi içeri aktarılan bir işlevin adresi alınırsa, DLL'de yer alan işlevin adresi döndürülür. Bu davranış, satır içi olmayan içeri aktarılmış bir işlevin adresini almakla aynıdır.

Tek bir programda (yani, DLL arabirimi olmayan yürütülebilir dosyası) gibi statik yerel veriler ve dizeler satır içi işlevler, DLL ve istemci arasında aynı kimlikleri korur.

İçeri aktarılan satır içi işlevleri sağlarken dikkatli olun. Örneğin, DLL'yi güncelleştirirseniz, istemcinin değiştirilmiş DLL sürümünü kullanacağını varsaymayın. DLL'nin doğru sürümünü yüklediğinizden emin olmak için DLL'nin istemcisini de yeniden oluşturun.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[DLL İçeri ve Dışarı Aktarma İşlevleri](../c-language/dll-import-and-export-functions.md)
