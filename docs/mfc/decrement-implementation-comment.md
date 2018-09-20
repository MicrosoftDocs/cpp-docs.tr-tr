---
title: --Uygulama açıklaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 874c7eb29f1908e6098ee4a9095f17a4dae00006
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402128"
---
# <a name="-implementation-comment"></a>// Uygulama Açıklaması

`// Implementation` Bölümü herhangi bir MFC sınıf bildiriminin en önemli parçasıdır.

Bu bölümde, tüm uygulama ayrıntılarını barındırır. Bu bölümde, hem üye değişkenleri ve üye işlevleri görünebilir. Bu satırın altındaki her şeyi MFC gelecekteki bir sürümde değişebilir. Bunu yoksayılamaz sürece ayrıntıları aşağıda doğrulamamalısınız `// Implementation` satır. Bazı uygulama teknik notları ele alınmıştır, ancak Ayrıca, uygulama satırın altına bildirilen üyeler, açıklanmamıştır. Bir işlev temel sınıf uygulamasına geçersiz kılmalar olgu bir uygulama ayrıntısı olduğu kabul edildiği için bağımsız olarak hangi bölümde temel sınıf işlevi, tanımlanan bu bölümde, temel sınıfta sanal işlevleri geçersiz kılmalarına bulunur. Genellikle, bu üyeler korunur, ama her zaman kullanılmaz.

Gelen fark `CStdioFile` altında listeleme [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md) aşağıda bildirilen üyeler `// Implementation` yorum olarak belirtilebilir **genel**, **korumalı**, veya **özel**. Gelecekte değişebilir olduğundan yalnızca bu üyeleri, dikkatli kullanmanız gerekir. Bir grubu üye olarak bildirmek **genel** için sınıf kitaplığı uygulamasının düzgün çalışması gerekli olabilir. Ancak, bu şekilde bildirilen üyeler güvenli bir şekilde kullanıyor olabileceği anlamına gelmez.

> [!NOTE]
>  Üzerinde veya altında kalan türlerinin açıklamaları bulabilirsiniz `// Implementation` açıklaması. Her iki durumda da, bunlar bunları bildirilen üyeler türlerini açıklar. Aşağıda oluşursa `// Implementation` açıklama varsayar üyeleri sürümlerdeki MFC gelecekte değişebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Kaynak Dosyalarını Kullanma](../mfc/using-the-mfc-source-files.md)<br/>
[Açıklamalara Bir Örnek](../mfc/an-example-of-the-comments.md)<br/>
[/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)<br/>
[Özniteliklerle ilgili açıklama](../mfc/decrement-attributes-comment.md)<br/>
[/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)<br/>
[Geçersiz kılınabilen öğelerle ilgili açıklama](../mfc/decrement-overridables-comment.md)

