---
title: --Oluşturucu açıklaması
ms.date: 11/04/2016
helpviewer_keywords:
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
ms.openlocfilehash: ee36ad991f2a19211b494010d6ff0a5338b80557
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480710"
---
# <a name="-constructors-comment"></a>// Oluşturucu Açıklaması

`// Constructors` Bir MFC sınıfı bildirimi bölümünü oluşturucularda (C++ anlamında) yanı sıra gerçekten nesnesini kullanmak için gerekli tüm başlatma işlevleri bildirir. Örneğin, `CWnd::Create` önce kullandığınız oluşturucular bölümünde çünkü `CWnd` nesnesi, bu gerekir "tam olarak oluşturulmasını" ilk C++ yapılandırıcının çağrılmasıyla ve ardından arama `Create` işlevi. Genellikle, bu üyeler ortaktır.

Örneğin, sınıf `CStdioFile` biri altında listesinde gösterilir, üç Oluşturucusu vardır [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md).

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Kaynak Dosyalarını Kullanma](../mfc/using-the-mfc-source-files.md)<br/>
[Uygulama açıklaması](../mfc/decrement-implementation-comment.md)<br/>
[Özniteliklerle ilgili açıklama](../mfc/decrement-attributes-comment.md)<br/>
[/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)<br/>
[Geçersiz kılınabilen öğelerle ilgili açıklama](../mfc/decrement-overridables-comment.md)

