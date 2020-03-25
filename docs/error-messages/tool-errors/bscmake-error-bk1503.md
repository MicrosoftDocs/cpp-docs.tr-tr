---
title: BSCMAKE Hatası BK1503
ms.date: 11/04/2016
f1_keywords:
- BK1503
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
ms.openlocfilehash: e0f05b3979024cb053394c51fa9337197b5de7bf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197866"
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE Hatası BK1503

' filename ' dosyasına yazılamıyor [: Reason]

BSCMAKE, derleme sırasında oluşturulan. sbr dosyalarını tek bir tarayıcı veritabanında birleştirir. Elde edilen tarayıcı veritabanı 64 MB 'yi aşarsa veya giriş (. sbr) dosyaları sayısı 4092 ' i aşarsa, bu hata yayınlanır.

Sorun 4092. sbr dosyalarından kaynaklanmasından kaynaklanıyorsa, giriş dosyalarının sayısını azaltmanız gerekir. Visual Studio 'Nun içinden bu, tüm projenizde [/fr](../../build/reference/fr-fr-create-dot-sbr-file.md) tarafından gerçekleştirilebilir ve sonra dosya temelinde bir dosya üzerinde yeniden denetim elde edilebilir.

Soruna 64MB 'den büyük bir. bsc dosyası neden olduysa, giriş olarak. sbr dosyalarının sayısını azaltmak elde edilen. bsc dosyasının boyutunu düşürür. Ayrıca, göz at bilgisi miktarı/em (makro genişletilmiş sembolleri hariç tut),/el (yerel değişkenleri hariç tut) ve/es (sistem dosyalarını hariç tut) kullanılarak azaltılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[BSCMAKE Seçenekleri](../../build/reference/bscmake-options.md)
