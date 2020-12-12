---
description: 'Hakkında daha fazla bilgi edinin: çok baytlı karakter kümeleri (MBCSs) desteği'
title: Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- multibyte characters [C++]
- MBCS [C++]
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
ms.openlocfilehash: 8ab6af7aa77942b39785faf68ea6a530867abff8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335776"
---
# <a name="support-for-multibyte-character-sets-mbcss"></a>Çok Baytlı Karakter Kümesi Desteği (MBCS'ler)

Çok baytlı karakter kümeleri (MBCSs), tek bir baytta temsil edilemeyecek olan Japonca ve Çince gibi karakter kümelerini destekleme gereksinimlerine yönelik daha eski bir yaklaşımdır. Yeni geliştirme yapıyorsanız, son kullanıcılar tarafından görülmeyen sistem dizeleri hariç tüm metin dizeleri için Unicode kullanmanız gerekir. MBCS eski bir teknolojidir ve yeni geliştirme için önerilmez.

En yaygın MBCS uygulamaları çift baytlık karakter kümeleridir (DBCSs). Genel olarak Visual C++ ve MFC özellikle, DBCS için tamamen etkinleştirilmiştir.

Örnekler için bkz. MFC kaynak kodu dosyaları.

Dilleri büyük karakter kümesi kullanan pazarlarda kullanılan platformlar için, Unicode için en iyi seçenek MBCS 'dir. MFC, Uluslararası veri türleri ve C çalışma zamanı işlevlerini kullanarak MBCS 'yi destekler. Kodunuzda aynı yapmanız gerekir.

MBCS 'nin altında, karakterler 1 veya 2 bayt olarak kodlanır. 2 bayt karakter, ilk veya ön bayt olarak, hem hem de aşağıdaki baytın tek bir karakter olarak yorumlandığını bildirir. İlk bayt, ön bayt olarak kullanılmak üzere ayrılmış bir kod aralığından gelir. Hangi bayt aralıklarının ön bayt olabileceği, kullanımda olan kod sayfasına bağlıdır. Örneğin, Japon kod sayfası 932, 0x81 ile 0x9F arası aralığını ön bayt olarak kullanır, ancak Korece kod sayfası 949 farklı bir Aralık kullanır.

MBCS programlarınızdaki tüm aşağıdakileri göz önünde bulundurun.

Ortamdaki MBCS karakterleri MBCS karakterleri dosya ve Dizin adları gibi dizelerde bulunabilir.

### <a name="editing-operations"></a>İşlemleri Düzenle

MBCS uygulamalarında düzenlenen işlemler, bayt değil, karakterler üzerinde çalışır. Giriş işareti bir karakteri bölmemelidir, **sağ ok** tuşu bir karakter sağa hareket etmelidir ve bu şekilde devam eder. **Delete** bir karakteri silmelidir; **Geri al** , yeniden ekleyin.

### <a name="string-handling"></a>Dize işleme

MBCS kullanan bir uygulamada, dize işleme özel sorunlar doğurur. Her iki genişlikteki karakterler tek bir dizede karıştırılır; Bu nedenle, ön bayt sayısını denetlemeyi unutmayın.

### <a name="run-time-library-support"></a>Çalışma zamanı kitaplık desteği

C çalışma zamanı kitaplığı ve MFC tek baytlık, MBCS ve Unicode programlamayı destekler. Tek baytlık dizeler `str` çalışma zamanı işlevleri ailesiyle işlenir, MBCS dizeleri karşılık gelen `_mbs` işlevlerle Işlenir ve Unicode dizeleri karşılık gelen `wcs` işlevlerle işlenir. MFC sınıfı üye işlev uygulamaları, doğru koşullarda normal `str` işlevler ailesi, MBCS işlevleri veya "MBCS/UNICODE taşınabilirlik" bölümünde açıklandığı gibi Unicode işlevleri eşleyen, taşınabilir çalışma zamanı işlevlerini kullanır.

### <a name="mbcsunicode-portability"></a>MBCS/Unicode taşınabilirlik

Tchar. h üstbilgi dosyasını kullanarak, aynı kaynaklardan tek baytlı, MBCS ve Unicode uygulamaları oluşturabilirsiniz. Tchar. h,  `str` `_mbs` `wcs` uygun şekilde, veya işlevlerine eşlenen _tcs ön eki eklenmiş makroları tanımlar. MBCS oluşturmak için, sembolünü tanımlayın `_MBCS` . Unicode oluşturmak için simgeyi tanımlayın `_UNICODE` . Varsayılan olarak `_UNICODE` MFC uygulamaları için tanımlanmıştır. Daha fazla bilgi için, bkz. [Tchar. h 'de Genel metin eşlemeleri](../text/generic-text-mappings-in-tchar-h.md).

> [!NOTE]
> Hem hem de tanımlarsanız davranış tanımsızdır `_UNICODE` `_MBCS` .

Mbctype. h ve mbstring. h üst bilgi dosyaları, bazı durumlarda ihtiyacınız olabilecek MBCS 'ye özgü işlevleri ve makroları tanımlar. Örneğin, `_ismbblead` bir dizedeki belirli bir baytın bir ön bayt olup olmadığını söyler.

Uluslararası taşınabilirlik için programınızı [Unicode](../text/support-for-unicode.md) veya çok baytlı karakter kümeleriyle (MBCSs) kodlayın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Programmda MBCS 'yi etkinleştirme](../text/international-enabling.md)

- [Programmda hem Unicode hem de MBCS 'yi etkinleştir](../text/internationalization-strategies.md)

- [Uluslararası bir program oluşturmak için MBCS 'yi kullanma](../text/mbcs-programming-tips.md)

- [MBCS programlama özetine bakın](../text/mbcs-programming-tips.md)

- [Bayt genişlikli taşınabilirlik için genel metin eşlemeleri hakkında bilgi edinin](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)<br/>
[Visual C++'ta MBCS Desteği](../text/mbcs-support-in-visual-cpp.md)
