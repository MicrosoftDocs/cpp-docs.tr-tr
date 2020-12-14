---
description: 'Daha fazla bilgi edinin: TN032: MFC özel durum mekanizması'
title: 'TN032: MFC Özel Durum Mekanizması'
ms.date: 11/04/2016
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
ms.openlocfilehash: 847d78762aaf5e04c8a0c1eb2170e951d0b867bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215540"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC Özel Durum Mekanizması

Önceki Visual C++ sürümleri standart C++ özel durum mekanizmasını desteklememiş ve MFC tarafından desteklenen makroları **deneyin/catch/throw** tarafından kullanıldı. Visual C++ bu sürümü C++ özel durumlarını tam olarak destekler. Bu notta, yığın tabanlı nesneleri otomatik olarak temizleme dahil olmak üzere önceki makroların bazı gelişmiş uygulama ayrıntıları ele alınmıştır. C++ özel durumları, varsayılan olarak yığın geri sarma özelliğini desteklediği için bu teknik nota artık gerek yoktur.

MFC makroları ve yeni C++ anahtar sözcükleri arasındaki farklılıklar hakkında daha fazla bilgi için bkz. [özel durumlar: MFC makroları ve C++ özel durumları kullanma](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
