---
description: 'Hakkında daha fazla bilgi edinin: dosya durumuna erişme'
title: Dosya Durumuna Erişme
ms.date: 11/04/2016
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
ms.openlocfilehash: defff16ddfb8cb5321def898cad451f1e12f1f8c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169534"
---
# <a name="accessing-file-status"></a>Dosya Durumuna Erişme

`CFile` Ayrıca dosyanın mevcut, oluşturma ve değiştirme tarihleri ve saatleri, mantıksal boyut ve yol dahil olmak üzere dosya durumunu almayı da destekler.

### <a name="to-get-file-status"></a>Dosya durumunu almak için

1. Bir dosya hakkında bilgi almak ve ayarlamak için [CFile](reference/cfile-class.md) sınıfını kullanın. Kullanışlı bir uygulama, `CFile` bir dosyanın var olup olmadığını anlamak Için **GetStatus** statik üye işlevini kullanmaktır. **GetStatus** , belirtilen dosya mevcut değilse 0 değerini döndürür.

Bu nedenle, aşağıdaki örnekte gösterildiği gibi, bir dosya açılırken **CFile:: modeCreate** bayrağını kullanıp kullanmayacağınızı öğrenmek için **GetStatus** sonucunu kullanabilirsiniz:

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

İlgili bilgiler için bkz. [serileştirme](serialization-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar](files-in-mfc.md)
