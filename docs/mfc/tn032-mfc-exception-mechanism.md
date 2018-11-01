---
title: 'TN032: MFC Özel Durum Mekanizması'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.exceptions
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
ms.openlocfilehash: f3f13bb40151d3b9ef0d57c7e769ca30fa629177
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633402"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC Özel Durum Mekanizması

Visual C++'ın önceki sürümlerini standart C++ özel durum mekanizması desteği ve MFC makroları sağlanan **TRY/CATCH/THROW** , bunun yerine kullanıldığını. Visual C++'ın bu sürümü, C++ özel durumlarını tam olarak destekler. Bu Not önceki makroları Gelişmiş uygulama ayrıntılarını bazıları ele da dahil olmak üzere otomatik olarak temizleme temel yığın nesneleri. C++ özel durumlarını yığını varsayılan olarak geriye doğru izleme desteklemediğinden, bu Teknik Not artık gerekli değildir.

Başvurmak [özel durumlar: MFC makrolarını ve C++ özel durumlarını](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) MFC makroları ve yeni C++ anahtar sözcükleri arasındaki farklar hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

