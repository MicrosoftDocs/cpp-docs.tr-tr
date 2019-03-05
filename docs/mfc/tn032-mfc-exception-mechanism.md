---
title: 'TN032: MFC özel durum mekanizması'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.exceptions
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
ms.openlocfilehash: 210e47e117cd602ba77edd330205385f54199ce5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288759"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC özel durum mekanizması

Visual C++'ın önceki sürümlerini standart C++ özel durum mekanizması desteği ve MFC makroları sağlanan **TRY/CATCH/THROW** , bunun yerine kullanıldığını. Visual C++'ın bu sürümü, C++ özel durumlarını tam olarak destekler. Bu Not önceki makroları Gelişmiş uygulama ayrıntılarını bazıları ele da dahil olmak üzere otomatik olarak temizleme temel yığın nesneleri. C++ özel durumlarını yığını varsayılan olarak geriye doğru izleme desteklemediğinden, bu Teknik Not artık gerekli değildir.

Başvurmak [özel durumlar: MFC makroları ve C++ özel durumlarını kullanma](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) MFC makroları ve yeni C++ anahtar sözcükleri arasındaki farklar hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
