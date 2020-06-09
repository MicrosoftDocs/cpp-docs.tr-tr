---
title: Seri Hale Getirme Mekanizmasını Atlama
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
ms.openlocfilehash: f47cac34f6cdbdae01af98ec28be5af17edf0e25
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620957"
---
# <a name="bypassing-the-serialization-mechanism"></a>Seri Hale Getirme Mekanizmasını Atlama

Gördüğünüze göre Framework, dosyalara ve dosyalardan veri okuma ve yazma için varsayılan bir yol sağlar. Bir arşiv nesnesi aracılığıyla serileştirmek, harika birçok uygulamanın ihtiyaçlarını karşılayacak. Bu tür bir uygulama bir dosyayı tamamen belleğe okur, kullanıcının dosyayı güncelleştirmesine izin verir ve ardından güncelleştirilmiş sürümü diske yeniden yazar.

Ancak, bazı uygulamalar verileri çok farklı şekilde çalışır ve bir arşiv aracılığıyla bu uygulamalar için serileştirme uygun değildir. Örnek olarak, veritabanı programları, yalnızca büyük dosyaların parçalarını düzenleme, salt metin dosyalarını yazan programlar ve veri dosyalarını paylaşan programlar sayılabilir.

Bu durumlarda, [CArchive](reference/carchive-class.md) nesnesi yerine bir [CFile](reference/cfile-class.md) nesnesi aracılığıyla dosya eylemlerini aracılık için [serileştirme](reference/cobject-class.md#serialize) işlevini farklı bir şekilde geçersiz kılabilirsiniz.

Sınıfın,,, `Open` `Read` `Write` `Close` ve `Seek` üye işlevlerini kullanarak `CFile` bir dosyayı açabilir, dosya işaretçisini (Seek) dosyada belirli bir noktaya taşıyabilir, bu noktada bir kaydı (belirtilen bayt sayısı) okuyabilir, kullanıcının kaydı güncelleştirmesine izin verebilir ve kaydı dosyaya geri yazalım. Çerçeve, dosyayı sizin için açar ve `GetFile` sınıfının üye işlevini kullanarak `CArchive` nesneye bir işaretçi elde edebilirsiniz `CFile` . Daha da karmaşık ve esnek kullanım açısından, sınıfının [OnOpenDocument](reference/cdocument-class.md#onopendocument) ve [OnSaveDocument](reference/cdocument-class.md#onsavedocument) üye işlevlerini geçersiz kılabilirsiniz `CWinApp` . Daha fazla bilgi için bkz. *MFC başvurusunda*sınıf [CFile](reference/cfile-class.md) .

Bu senaryoda, `Serialize` bir dosya üst bilgisi okumak ve yazmak istiyorsanız belge kapandığında bir dosya üstbilgisi okuyup yazmak istiyorsanız, geçersiz kılma hiçbir şey yapmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri kullanma](using-documents.md)
