---
title: Zincirleme Bırakma bilgi yapıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6da09387595188026d855fb99a49b588e6f21aa3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715032"
---
# <a name="chained-unwind-info-structures"></a>Zincirleme Bırakma Bilgi Yapıları

UNW_FLAG_CHAININFO bayrağı ayarlandıysa, bir geriye doğru izleme bilgisi yapısı ikincil bir ise ve paylaşılan özel durum işleyicisi/zincirleme-bilgisi adres alanı birincil geriye doğru izleme bilgileri içerir. Aşağıdaki kod alır, birincil bilgi olduğunu varsayarak, geriye doğru izleme `unwindInfo` kümesine sahip yapı bayrağı ayarlanmış olduğu.

```
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

Zincir bilgisi iki durumlarda yararlı olur. İlk olarak, bitişik olmayan kod parçaları için kullanılabilir. Zincirleme bilgileri kullanarak, birincil geriye doğru izleme bilgisi geriye doğru izleme kodları diziden yinelenen olmadığı için gerekli geriye doğru izleme bilgileri boyutunu azaltabilirsiniz.

Zincirleme bilgi, geçici kayıtları gruplamak için de kullanabilirsiniz. Derleyici, işlev girişi giriş dışında oluncaya kadar bazı geçici kayıtları geciktirebilir. Bu işlev gruplandırılmış kodundan önce kısmı için birincil geriye doğru izleme bilgileri sağlayarak kaydedin ve ardından ayarlama burada geriye doğru izleme kodları zincirleme bilgileri kalıcı yazmaçların kaydeder yansıttığı sıfır boyutlu bilgisi zincirleme. Bu durumda, geriye doğru izleme kodları tüm UWOP_SAVE_NONVOL örnekleridir. Bir anında İLETME kullanarak kalıcı Yazmaçları kaydeder veya bir sabit ek yığın ayırma kullanarak RSP kaydı değiştirir, bir gruplandırma desteklenmiyor.

UNWIND_INFO öğesi de (birden çok sabit) kümesi kümesine sahip bir RUNTIME_FUNCTION girişi Ayarla kümesine sahip bir UNWIND_INFO öğe içerebilir. Sonuç olarak, zincirleme işaretçileri, temizlenmiş kümesine sahip bir UNWIND_INFO öğe ulaşır bilgilerindeki; Gerçek yordam giriş noktasına işaret birincil UNWIND_INFO öğesi budur.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme için Veri Bırakma, Hata Ayıklayıcı Desteği](../build/unwind-data-for-exception-handling-debugger-support.md)