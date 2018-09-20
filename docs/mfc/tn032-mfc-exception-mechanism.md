---
title: 'TN032: MFC özel durum mekanizması | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.exceptions
dev_langs:
- C++
helpviewer_keywords:
- TN032
- MFC, exceptions
- CException class [MFC], using
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aee8ce02af874e1c3c30243a35e8f36acfce63f0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414764"
---
# <a name="tn032-mfc-exception-mechanism"></a>TN032: MFC Özel Durum Mekanizması

Visual C++'ın önceki sürümlerini standart C++ özel durum mekanizması desteği ve MFC makroları sağlanan **TRY/CATCH/THROW** , bunun yerine kullanıldığını. Visual C++'ın bu sürümü, C++ özel durumlarını tam olarak destekler. Bu Not önceki makroları Gelişmiş uygulama ayrıntılarını bazıları ele da dahil olmak üzere otomatik olarak temizleme temel yığın nesneleri. C++ özel durumlarını yığını varsayılan olarak geriye doğru izleme desteklemediğinden, bu Teknik Not artık gerekli değildir.

Başvurmak [özel durumlar: MFC makrolarını ve C++ özel durumlarını](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) MFC makroları ve yeni C++ anahtar sözcükleri arasındaki farklar hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

