---
title: Bağlayıcı Komut Satırı Sözdizimi
ms.date: 11/04/2016
helpviewer_keywords:
- linker [C++], syntax
- linker command line [C++]
- LINK tool [C++], command-line syntax
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
ms.openlocfilehash: 55171c1f16b43e08b5c4a6b078c82f4ed08855d5
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422734"
---
# <a name="linker-command-line-syntax"></a>Bağlayıcı Komut Satırı Sözdizimi

BAĞLANTI çalıştırılacak. EXE, aşağıdaki komut söz dizimini kullanın:

```
LINK arguments
```

`arguments` Seçenekleri ve dosya adları içerir ve herhangi bir sırada belirtilebilen. Seçenekler şunlardır: ilk işlenen, sonra da dosyaları. Bir veya daha fazla boşluk veya sekme bağımsız değişkenleri ayırmak için kullanın.

> [!NOTE]
>  Bu araç yalnızca Visual Studio komut isteminden başlatabilirsiniz. Bir sistem komut satırından veya dosya Gezgini'nden başlatılamıyor.

Komut satırında bir seçenek bir seçenek belirleyicisinden oluşur. bir tire (-) veya eğik çizgi (/) seçeneğinin adı tarafından izlenen. Seçenek adları kısaltılmış olamaz. Bazı seçenekler bir iki nokta (:) sonra belirtilen bir bağımsız değişken alan. Boşluk veya sekme bir seçenek belirtimi içinde dışında/Comment seçeneğinde alıntılanmış dize içinde izin verilir. Ondalık veya C dili gösterimi sayısal bağımsız değişkenleri belirtin. Seçenek adları ve anahtar sözcüğü veya dosya adı bağımsız değişkenler büyük küçük harfe duyarlı değildir, ancak bağımsız değişken olarak tanımlayıcıları büyük küçük harf duyarlıdır.

Bağlayıcı için bir dosya geçirmek için dosya adı bağlantı komutundan sonra komut satırında belirtin. Mutlak veya göreli bir yol ile dosya adını belirtin ve dosya adında joker karakterler kullanabilirsiniz. Nokta (.) ve dosya adı uzantısı atlarsanız, bağlantı .obj dosyası bulma amacıyla varsayar. BAĞLANTI eksikliği veya dosya adı uzantıları dosyaların içeriği hakkında varsayımlar yapmak kullanmaz; Dosya türü, inceleyerek belirler ve buna göre işler.

Link.exe başarı durumunda (hatasız) sıfır döndürür.  Aksi takdirde bağlayıcı bağlantı durduruldu hata numarasını döndürür.  Örneğin, bağlayıcı LNK1104 oluşturursa, bağlayıcı 1104 döndürür.  Buna göre bir hatada bağlayıcı tarafından döndürülen en düşük hata sayısı 1000'dir.  128 dönüş değeri bir yapılandırma sorunu işletim sisteminde veya .config dosyasını temsil eder; Yükleyici link.exe ya da c2.dll yüklenmedi.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
