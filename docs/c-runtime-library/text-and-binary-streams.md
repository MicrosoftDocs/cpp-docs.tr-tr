---
title: Metin ve İkili Akışlar
description: Microsoft C çalışma zamanı kitaplığındaki metin ve ikili akışların açıklaması.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- binary streams
- text streams
ms.assetid: 57035e4a-955d-4e04-a560-fcf67ce68b4e
ms.openlocfilehash: 522e4d5f119e4415694b59b2b08141a45f06fe5a
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91589620"
---
# <a name="text-and-binary-streams"></a>Metin ve İkili Akışlar

Bir metin akışı, okunabilecek bir veya daha fazla metin satırından oluşur ve böylece okunabilmeleri için metin yönelimli bir görüntülemeye yazılabilir. Bir metin akışından okurken, program `NL` her satırın sonundaki bir (yeni satır) okur. Bir metin akışına yazarken, program bir `NL` satırın sonuna bir sinyal yazar. Dosyalardaki metni göstermek için hedef ortamlar arasındaki farklı kuralları eşleştirmek için kitaplık işlevleri, program ve metin akışı arasında aktarılan karakterlerin sayısını ve temsilini değiştirebilir.

Bir metin akışı içinde konumlandırma sınırlıdır. [Fgetpos](../c-runtime-library/reference/fgetpos.md) veya [FINFO](../c-runtime-library/reference/ftell-ftelli64.md)çağırarak geçerli dosya konumu göstergesini elde edebilirsiniz. Bir metin akışını bu şekilde alınan bir konuma veya akışın başında ya da sonunda, [fsetpos](../c-runtime-library/reference/fsetpos.md) veya [fseek](../c-runtime-library/reference/fseek-fseeki64.md)çağırarak yerleştirebilirsiniz. Diğer konum değişikliği de desteklenmiyor olabilir.

Maksimum taşınabilirlik için program şunu yazmamalıdır:

- Boş dosyalar.
- Satırın sonundaki boşluk karakterleri.
- Kısmi satırlar ( `NL` bir dosyanın sonunda öğesini atlayarak).
- yazdırılabilir karakterler, NL ve `HT` (yatay sekme) dışındaki karakterler.

Bu kuralları izlerseniz, bir metin akışından (bayt veya çok baytlı karakterler olarak) yazdığınız karakterlerin sırası, dosyayı oluştururken metin akışına yazdığınız karakter dizisiyle eşleşir. Aksi halde, dosyayı kapattığınızda dosya boşsa, kitaplık işlevleri oluşturduğunuz bir dosyayı kaldırabilir. Ya da dosyaya yazdığınız karakterleri değiştirebilir veya silebilir.

İkili akış, bir veya daha fazla isteğe bağlı bilgi içeren bir bayt içerir. Rastgele bir nesnede depolanan değeri (bayt yönelimli) ikili bir akışa yazabilir ve yazdığınızda nesne içinde nelerin depolanabileceğini tam olarak okuyabilirsiniz. Kitaplık işlevleri, program ve ikili akış arasında gönderdiğiniz baytları değiştirmez. Ancak, `NULL` ikili bir akışa yazdığınız dosyaya rastgele sayıda bayt ekler. Program, `NULL` ikili akışın sonundaki bu ek baytlarla uğraşmalıdır.

Bir ikili akış içinde konumlandırmanın, akışın sonuna göre konumlandırması dışında iyi tanımlanmış olması gerekir. Geçerli dosya konumu göstergesini bir metin akışı ile aynı şekilde alabilir ve değiştirebilirsiniz. [Fsöyleyin](../c-runtime-library/reference/ftell-ftelli64.md) ve [fseek](../c-runtime-library/reference/fseek-fseeki64.md) sayısı baytları akışın başından (bayt sıfır), bu nedenle bu uzaklıklardaki tamsayı aritmetiği öngörülebilir sonuçlar verir.

Bayt akışı bir dosyayı bir bayt dizisi olarak değerlendirir. Program içinde akış, yukarıda açıklanan olası düzeltmeler dışında aynı bayt dizisine benzer şekilde görünür.

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar ve akışlar](../c-runtime-library/files-and-streams.md)
