---
title: --İşlem açıklaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Operations comment in MFC source files
- comments, MFC
- MFC source files, Operations comments
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73c4a7a70c9f2ed987337426793bd462c2a94309
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372502"
---
# <a name="-operations-comment"></a>// İşlem Açıklaması

`// Operations` Bir MFC sınıfı bildirimi bölümü işlemleri veya eylemleri (işlemleri gerçekleştirme) sağlamak için bir nesnede çağırabilirsiniz üye işlevleri içerir. Bu işlevler genellikle olmayan**const** genellikle sahip oldukları yan etkiler. Bunlar, sanal veya sanal olmayan sınıf gereksinimlerine bağlı olarak olabilir. Genellikle, bu üyeler ortaktır.

Sınıf listesi örneği'nde `CStdioFile`, [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md), liste bu açıklamayı altında iki üye işlevleri içerir: `ReadString` ve `WriteString`.

Özniteliklerle yönteminde olduğu gibi işlemler daha fazla alt bölümlere ayrılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Kaynak Dosyalarını Kullanma](../mfc/using-the-mfc-source-files.md)<br/>
[Açıklamalara Bir Örnek](../mfc/an-example-of-the-comments.md)<br/>
[Uygulama açıklaması](../mfc/decrement-implementation-comment.md)<br/>
[/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)<br/>
[Özniteliklerle ilgili açıklama](../mfc/decrement-attributes-comment.md)<br/>
[Geçersiz kılınabilen öğelerle ilgili açıklama](../mfc/decrement-overridables-comment.md)

