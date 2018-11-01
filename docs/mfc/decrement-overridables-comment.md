---
title: --Geçersiz kılınabilen öğelerle ilgili açıklama
ms.date: 11/04/2016
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
ms.openlocfilehash: 9efba74676ba118659601522fc915bf25f607116
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554178"
---
# <a name="-overridables-comment"></a>// Geçersiz Kılınabilen Öğelerle İlgili Açıklama

`// Overridables` Bölümü bir MFC sınıf bildiriminin temel sınıf davranışını değiştirmek, ihtiyacınız olduğunda, türetilen bir sınıfta geçersiz kılabilirsiniz sanal işlevler içerir. Kesinlikle gerekli olmasa da bunlar genellikle "ile", başlangıç olarak adlandırılır. Burada işlevleri geçersiz kılınması, genellikle uygulamak veya "geri" veya "kanca" çeşit sağlamak için tasarlanmıştır Genellikle, bu üyeler korunur.

MFC'de kendisi, saf sanal işlevler, her zaman bu bölümde yerleştirilir. C++'ta saf sanal işlevi, formu biridir:

`virtual void OnDraw( ) = 0;`

Sınıf listesi örneği'nde `CStdioFile`, [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md), liste geçersiz kılınabilen öğelerle ilgili bölüm içerir. Sınıf `CDocument`, diğer taraftan, yaklaşık 10 geçersiz kılınabilir üye işlevleri listeler.

Bazı sınıflarda da yorumu görebilirsiniz `// Advanced Overridables`. Bunlar yalnızca gelişmiş işlevleri programcılar geçersiz kılma girişiminde. Muhtemelen hiçbir zaman bunları geçersiz kılmak gerekir.

> [!NOTE]
>  Bu makalede açıklanan kuralları aynı zamanda da genel olarak, otomasyon (eski adıyla OLE Otomasyonu da bilinir) yöntemleri ve özellikleri için çalışır. Otomasyon yöntemleri MFC işlemlerine benzer. Otomasyon özellikleri, MFC öznitelikleri benzerdir. Otomasyon olaylarına (eski adı OLE denetimleri bilinen, ActiveX denetimleri için desteklenir) için MFC geçersiz kılınabilir üye işlevleri benzerdir.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Kaynak Dosyalarını Kullanma](../mfc/using-the-mfc-source-files.md)<br/>
[Açıklamalara Bir Örnek](../mfc/an-example-of-the-comments.md)<br/>
[Uygulama açıklaması](../mfc/decrement-implementation-comment.md)<br/>
[/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)<br/>
[Özniteliklerle ilgili açıklama](../mfc/decrement-attributes-comment.md)<br/>
[/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)

