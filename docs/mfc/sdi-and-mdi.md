---
title: SDI ve MDI | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8189af7939bfca0fd206fa72892098e373444879
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401452"
---
# <a name="sdi-and-mdi"></a>SDI ve MDI

MFC tek Belgeli Arabirim (SDI) ve Çok Belgeli Arabirim (MDI) uygulamaları ile çalışmak kolaylaştırır.

SDI uygulamaları yalnızca bir açık belge çerçeve penceresi bir kerede izin verin. MDI uygulamaları birden çok belge çerçeve pencereleri uygulama aynı örneğinde açık olmasını sağlar. Bir MDI uygulaması içeren her ayrı bir belge içinde birden çok hangi MDI çerçeve pencereleri kendilerini olan alt pencereleri açılabilen bir pencere içerir. Bazı uygulamalarda, alt öğe pencerelerini grafik windows ve elektronik windows gibi farklı türlerde olabilir. Bu durumda, MDI alt pencereleri farklı türlerde etkin menü çubuğunu değiştirebilirsiniz.

> [!NOTE]
>  İşletim sistemi "Belge merkezli" görünümü başlamıştır çünkü Windows 95 ve daha sonra yaygın olarak SDI uygulamalardır.

Daha fazla bilgi için [belgeler, görünümler ve çerçeve](../mfc/documents-views-and-the-framework.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Uygulamaları Yazmak için Sınıfları Kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
