---
title: /BIND
ms.date: 11/04/2016
f1_keywords:
- /bind
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
ms.openlocfilehash: e8ba0a5f0235c8771567e4e43172bdf8c81c99a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295038"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, bir yürütülebilir dosya veya DLL için içeri aktarma adres tablosunda giriş noktaları adreslerini belirler. Bir programın yükleme süresini azaltmak için bu seçeneği kullanın.

Programın yürütülebilir dosyayı ve DLL'ler belirtin *dosyaları* EDITBIN komut satırı bağımsız değişkeni. İsteğe bağlı *yolu*  /Bind bağımsız değişkeni tarafından belirtilen dosyalarını kullanılan dll konumunu belirtir. Birden çok dizinlerin noktalı virgülle ayırın (**;**). Varsa *yolu* belirtilmezse, EDITBIN yol ortam değişkeninde belirtilen dizinleri arar. Varsa *yolu* belirtilirse, EDITBIN PATH değişkenini yoksayar.

Bir program yüklendiğinde varsayılan olarak, giriş noktası adreslerini program yükleyicisi ayarlar. Bu işlem gereken süreyi DLL'leri sayısı ve programda başvurulan giriş noktası sayısını bağlı olarak değişir. Program/Bind ile değiştirdiyseniz ve yürütülebilir dosyasını temel giderir ve önceden yüklenen DLL dosyaları, DLL'ler çakışmadığından varsa, işletim sistemi bu adresleri kümesi gerekmez. Burada dosyaların yanlış dayalı bir durumda işletim sistemi programın DLL'leri yeniden yerleştirir ve giriş noktası adreslerini programın yükleme zamanını kabul ekleyen yeniden hesaplar.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
