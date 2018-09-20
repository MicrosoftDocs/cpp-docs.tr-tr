---
title: Belge şablonu sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document templates [MFC], classes
ms.assetid: 901749e9-8048-44a0-b5e2-361554650a73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87984bf06d8ca178d2a21ac8ff475f828690668e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406067"
---
# <a name="document-template-classes"></a>Belge Şablonu Sınıfları

Belge şablonu nesneleri belge, Görünüm ve çerçeve pencere nesneleri bir yeni belge oluşturma koordine etmek veya görünüm oluşturulur.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md)<br/>
Belge şablonları için temel sınıf. Hiçbir zaman doğrudan bu sınıfı kullanır; Bunun yerine, bu sınıftan türetilen diğer belge şablonu sınıfları birini kullanın.

[CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)<br/>
Çok Belgeli Arabirim (MDI) belgeler için bir şablon. MDI uygulamaları aynı anda birden çok belgeyi olabilir.

[CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md)<br/>
Tek Belgeli Arabirim (SDI) belgeler için bir şablon. SDI uygulamaları aynı anda yalnızca bir belge vardır.

## <a name="related-class"></a>İlgili sınıfı

[CCreateContext](../mfc/reference/ccreatecontext-structure.md)<br/>
Bir yapının bir belge şablonu tarafından belge, Görünüm ve çerçeve pencere nesnelerinin oluşturulması koordine etmek için pencere oluşturma işlevlerine geçirilen.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

