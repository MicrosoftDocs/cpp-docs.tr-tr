---
title: dllexport ve dllimport ile Satır İçin C++ İşlevlerini Tanımlama
ms.date: 11/04/2016
helpviewer_keywords:
- inline functions [C++], defining
- functions [C++], defining inline
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
ms.openlocfilehash: 88fbb497aab4d794d3ef84a902a72c4e044e51de
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857573"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>dllexport ve dllimport ile Satır İçin C++ İşlevlerini Tanımlama

**Microsoft 'a özgü**

**Dllexport** özniteliğiyle bir işlev olarak satır içi olarak tanımlayabilirsiniz. Bu durumda, programdaki herhangi bir modülün işleve başvurup başvurmadığına bakılmaksızın işlevin her zaman örneği oluşturulur ve işlev dışarı aktarılır. İşlevin, başka bir program tarafından içeri aktarıldığı varsayılır.

Ayrıca, **dllimport** özniteliğiyle belirtilen bir işlevi satır içi olarak tanımlayabilirsiniz. Bu durumda, işlev genişletilebilir (/Ob belirtimlerine tabidir), ancak örneği hiçbir zaman oluşturulamaz. Özellikle, satır içi içeri aktarılan bir işlevin adresi alınırsa, DLL'de yer alan işlevin adresi döndürülür. Bu davranış, satır içi olmayan içeri aktarılmış bir işlevin adresini almakla aynıdır.

Bu kurallar, tanımları bir sınıf tanımı içinde görünen satır içi işlevlere uygulanır. Ayrıca, satır içi işlevlerdeki statik yerel veriler ve dizeler, tek bir programda (yani, DLL arabirimi olmayan yürütülebilir bir dosya) olduğu gibi DLL ve istemci arasında aynı kimlikleri korur.

İçeri aktarılan satır içi işlevleri sağlarken dikkatli olun. Örneğin, DLL'yi güncelleştirirseniz, istemcinin değiştirilmiş DLL sürümünü kullanacağını varsaymayın. DLL'nin doğru sürümünü yüklediğinizden emin olmak için DLL'nin istemcisini de yeniden oluşturun.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)