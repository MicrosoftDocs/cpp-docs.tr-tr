---
description: 'Hakkında daha fazla bilgi edinin: belge ve görünümleri Temizleme'
title: Belgeleri ve Görünümleri Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 73d7dcb94068499998ac05d76dd023b7274c6588
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176662"
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme

Bir belge kapatılırken, Framework ilk olarak [DeleteContents](reference/cdocument-class.md#deletecontents) üye işlevini çağırır. Belgenin işleminin kursu sırasında yığında herhangi bir bellek ayırdıysanız, `DeleteContents` serbest bırakmak için en iyi yer vardır.

> [!NOTE]
> Belgenin yıkıcısında belge verilerini serbest bırakma kullanmamalısınız. SDI uygulaması söz konusu olduğunda, belge nesnesi yeniden kullanılıyor olabilir.

Yığında ayrılan belleği serbest bırakmak için bir görünümün yıkıcısında geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri ve görünümleri başlatma ve Temizleme](initializing-and-cleaning-up-documents-and-views.md)
