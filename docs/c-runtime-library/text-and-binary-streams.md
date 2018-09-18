---
title: Metin ve ikili akışlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- binary streams
- text streams
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 106e02de80c3132846d7b88161637a37f74a59ee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068643"
---
# <a name="text-and-binary-streams"></a>Metin ve İkili Akışlar

Metin akışına bir veya daha fazla metin tabanlı bir görüntü için yazılabilir ve böylece bunlar okunabilir metin satırlarını oluşur. Bir metin akışından okuma sırasında program okur bir `NL` (yeni satır) her satırın sonunda. Bir metin akışına yazma, program Yazar bir `NL` bir satırın sonuna sinyal. Dosyalardaki metni temsil etmek için hedef ortamlar arasındaki farklı kuralları eşleştirmek için kitaplık işlevleri sayısı ve program ve metin akışına arasında aktarılan karakter temsillerini değiştirebilirsiniz.

Bu nedenle, bir metin akışına içinde konumlandırma sınırlıdır. Geçerli dosya konumu göstergesi çağırarak elde edebileceğiniz [fgetpos](../c-runtime-library/reference/fgetpos.md) veya [ftell](../c-runtime-library/reference/ftell-ftelli64.md). Çağırarak bu şekilde elde ettiğiniz konumda veya başlangıcında veya akışın sonuna metin akışına konumlandırabilirsiniz [fsetpos](../c-runtime-library/reference/fsetpos.md) veya [fseek](../c-runtime-library/reference/fseek-fseeki64.md). Herhangi bir değişiklik konumunun da desteklenmeyebilir.

En fazla taşınabilirlik için program yazma değil:

- Boş dosya.

- Bir satırın sonunda boşluk karakterleri.

- Kısmi satır (atlama tarafından `NL` dosya sonunda).

- dışında yazdırılabilir bir karakter, NL, karakterleri ve `HT` (yatay sekme).

Bu kurallar izlerseniz (veya bayt veya çok baytlı karakter olarak) metin akıştan okunan karakter dizisini dosyasını oluştururken metin akışına yazdığınız karakterlerin dizisiyle eşleşir. Aksi halde, kitaplık işlevleri kapatıldığında dosya boşsa, oluşturduğunuz bir dosya kaldırabilirsiniz. Veya alter veya dosyaya yazmak karakterleri silin.

İkili akışa bir veya daha fazla bilgi rastgele bayt oluşur. İkili akışa (bayt odaklı) için rastgele bir nesnede depolanan değeri yazın ve yazdığınız zaman tam olarak ne nesnesinde depolanan okuyun. Kitaplık işlevleri, program ve ikili akışa arasında iletim bayt değiştirmeyin. Bunlar ancak boş bayt rastgele bir sayıdan, bir ikili akışa yazmak dosya ekleyebilir. Programın sonunda herhangi bir ikili akışı, bu ek boş bayt uğraşmanız gerekir.

Bu nedenle, ikili bir akış içinde konumlandırma akışın sonuna göreli konumlandırma dışında iyi tanımlanmış. Alabilir ve aynı metin akışına geçerli dosya konumu göstergesi alter. Ayrıca, tarafından kullanılan uzaklıkları [ftell](../c-runtime-library/reference/ftell-ftelli64.md) ve [fseek](../c-runtime-library/reference/fseek-fseeki64.md) (sıfır bayt olan) akış başından itibaren bayt sayısı için tamsayı bu uzaklıkları üzerinde aritmetik tahmin edilebilir sonuçlar verir.

Bir bayt akışı, bir dosya bir bayt dizisi olarak değerlendirir. Bir program içindeki aynı yukarıda açıklanan olası değişiklikleri dışında bir bayt dizisini akış benzer.

## <a name="see-also"></a>Ayrıca Bkz.

[Dosyalar ve Akışlar](../c-runtime-library/files-and-streams.md)