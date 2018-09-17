---
title: -BIND | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /bind
dev_langs:
- C++
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a47004ce41d6bae3d91a81c4a61a712bc31dfbdb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725900"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, bir yürütülebilir dosya veya DLL için içeri aktarma adres tablosunda giriş noktaları adreslerini belirler. Bir programın yükleme süresini azaltmak için bu seçeneği kullanın.

Programın yürütülebilir dosyayı ve DLL'ler belirtin *dosyaları* EDITBIN komut satırı bağımsız değişkeni. İsteğe bağlı *yolu*  /Bind bağımsız değişkeni tarafından belirtilen dosyalarını kullanılan dll konumunu belirtir. Birden çok dizinlerin noktalı virgülle ayırın (**;**). Varsa *yolu* belirtilmezse, EDITBIN yol ortam değişkeninde belirtilen dizinleri arar. Varsa *yolu* belirtilirse, EDITBIN PATH değişkenini yoksayar.

Bir program yüklendiğinde varsayılan olarak, giriş noktası adreslerini program yükleyicisi ayarlar. Bu işlem gereken süreyi DLL'leri sayısı ve programda başvurulan giriş noktası sayısını bağlı olarak değişir. Program/Bind ile değiştirdiyseniz ve yürütülebilir dosyasını temel giderir ve önceden yüklenen DLL dosyaları, DLL'ler çakışmadığından varsa, işletim sistemi bu adresleri kümesi gerekmez. Burada dosyaların yanlış dayalı bir durumda işletim sistemi programın DLL'leri yeniden yerleştirir ve giriş noktası adreslerini programın yükleme zamanını kabul ekleyen yeniden hesaplar.

## <a name="see-also"></a>Ayrıca Bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)