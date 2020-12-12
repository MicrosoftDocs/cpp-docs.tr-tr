---
description: 'Daha fazla bilgi edinin: BSCMAKE hatası BK1503'
title: BSCMAKE Hatası BK1503
ms.date: 11/04/2016
f1_keywords:
- BK1503
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
ms.openlocfilehash: 0e789aa54241df5245f4c3a02a9307a97d51730c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323005"
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE Hatası BK1503

' filename ' dosyasına yazılamıyor [: Reason]

BSCMAKE, derleme sırasında oluşturulan. sbr dosyalarını tek bir tarayıcı veritabanında birleştirir. Elde edilen tarayıcı veritabanı 64 MB 'yi aşarsa veya giriş (. sbr) dosyaları sayısı 4092 ' i aşarsa, bu hata yayınlanır.

Sorun 4092. sbr dosyalarından kaynaklanmasından kaynaklanıyorsa, giriş dosyalarının sayısını azaltmanız gerekir. Visual Studio 'Nun içinden bu, tüm projenizde [/fr](../../build/reference/fr-fr-create-dot-sbr-file.md) tarafından gerçekleştirilebilir ve sonra dosya temelinde bir dosya üzerinde yeniden denetim elde edilebilir.

Soruna 64MB 'den büyük bir. bsc dosyası neden olduysa, giriş olarak. sbr dosyalarının sayısını azaltmak elde edilen. bsc dosyasının boyutunu düşürür. Ayrıca, göz at bilgisi miktarı/em (makro genişletilmiş sembolleri hariç tut),/el (yerel değişkenleri hariç tut) ve/es (sistem dosyalarını hariç tut) kullanılarak azaltılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[BSCMAKE seçenekleri](../../build/reference/bscmake-options.md)
