---
title: Bayt ve Geniş Akışlar
description: Microsoft C çalışma zamanı kitaplığı 'ndaki bayt akışlarına genel bakış.
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Byte and Wide Streams
helpviewer_keywords:
- byte streams
- wide streams
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
ms.openlocfilehash: 38949206e65ff84836b9a3e83b78723adfe30582
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91590283"
---
# <a name="byte-and-wide-streams"></a>Bayt ve Geniş Akışlar

Bayt akışı bir dosyayı bir bayt dizisi olarak değerlendirir. Program içinde, akış baytların özdeş sırasıdır.

Bunun aksine, geniş bir akış bir dosyayı, çok sayıda kodlama kuralına sahip olabilecek, genelleştirilmiş çok baytlı karakterlerin bir dizisi olarak değerlendirir. (Metin ve ikili dosyalar hala daha önce açıklanan şekilde okunabilir ve yazılır.) Program içinde akış, karşılık gelen geniş karakter dizisi gibi görünür. İki gösterimdeki dönüştürmeler standart C kitaplığında oluşur. Dönüştürme kuralları, prensibi, kategoriyi değiştiren bir [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) çağrısıyla değiştirilebilir `LC_CTYPE` . Her geniş akış, dönüştürme kurallarını geniş bir şekilde olduğu zaman belirler ve kategori daha sonra değişse bile bu kuralları korur `LC_CTYPE` .

Geniş bir akış içinde konumlandırması, metin çlarıyla aynı sınırlamaları ortadan kaldırmak. Ayrıca, dosya konumu göstergesinin bir durum bağımlı kodlamalı olması gerekebilir. Genellikle, akış içinde hem bayt sapmasını hem de türünde bir nesne içerir `mbstate_t` . Bu nedenle, geniş bir akışta dosya konumu almanın tek güvenilir yolu [fgetpos](../c-runtime-library/reference/fgetpos.md)' ı çağırarak ve bu şekilde elde edilen bir konumu geri yüklemenin tek güvenilir yolu [fsetpos](../c-runtime-library/reference/fsetpos.md)' ı çağırarak olur.

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar ve akışlar](../c-runtime-library/files-and-streams.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)
