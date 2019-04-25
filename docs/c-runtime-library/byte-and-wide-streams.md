---
title: Bayt ve Geniş Akışlar
ms.date: 11/04/2016
f1_keywords:
- Byte and Wide Streams
helpviewer_keywords:
- byte streams
- wide streams
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
ms.openlocfilehash: 67de6b609b3e0546d539ef9c37f12db1067546ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62290501"
---
# <a name="byte-and-wide-streams"></a>Bayt ve Geniş Akışlar

Bir bayt akışı, bir dosya bir bayt dizisi olarak değerlendirir. Program içindeki akış aynı bayt dizisidir.

Aksine, geniş bir akış geniş bir kodlama kuralları olabilir genelleştirilmiş çok baytlı karakter dizisi olarak bir dosyanın değerlendirir. (Metin ve ikili dosyalar hala okuyun ve daha önce açıklandığı gibi yazılan.) Bir program içindeki akış karşılık gelen geniş karakter dizisi gibi görünüyor. İki temsiller arasındaki dönüştürmeler, standart C Kitaplığı içinde oluşur. Dönüştürme kuralları İlkesi, bir çağrı tarafından değiştirilebilir [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) , kategori değiştirir `LC_CTYPE`. Her geniş akış dönüştürme kurallarını zaman geniş yönlendirilmiş olur ve bu kuralları bile korur belirler. kategori `LC_CTYPE` sonradan değiştirir.

Geniş bir akış içinde konumlandırma metin steams olduğu gibi aynı sınırlamalar düşer. Ayrıca, dosya konumu göstergesi iyi bir duruma bağlı kodlamayı ile uğraşmak zorunda kalabilirsiniz. Genellikle, akış ve türünde bir nesne içinde uzaklığı bir iki bayt içerir `mbstate_t`. Bu nedenle, geniş bir akış içinde bir dosya konumu almak için yalnızca güvenilir çağırarak yoludur [fgetpos](../c-runtime-library/reference/fgetpos.md), ve bu şekilde elde edilen bir konuma geri yüklemek için yalnızca güvenilir bir şekilde çağrılarak [fsetpos](../c-runtime-library/reference/fsetpos.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar ve Akışlar](../c-runtime-library/files-and-streams.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
