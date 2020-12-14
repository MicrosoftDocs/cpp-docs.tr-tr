---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1112'
title: Bağlayıcı Araçları Hatası LNK1112
ms.date: 11/04/2016
f1_keywords:
- LNK1112
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
ms.openlocfilehash: ba0a34e07b0806f251c0b1237dc28ab5f8becbf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281385"
---
# <a name="linker-tools-error-lnk1112"></a>Bağlayıcı Araçları Hatası LNK1112

> Modül makine türü '*Type1*', hedef makine türü '*type2*' ile çakışıyor

## <a name="remarks"></a>Açıklamalar

Giriş olarak belirtilen nesne dosyaları farklı bilgisayar türleri için derlendi.

Örneğin, **/clr** ile derlenen bir nesne dosyasını ve **/clr: Pure** (makine türü Cee) ile derlenen bir nesne dosyasını BAĞLAMAYı denerseniz, bağlayıcı LNK1112 hatasını oluşturacaktır. **/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Benzer şekilde, x64 derleyicisi ve x86 derleyicisine sahip başka bir modül ile bir modül oluşturursanız ve bu bağlantıları bağlamayı denerseniz, bağlayıcı LNK1112 oluşturur.

Bu hatanın olası bir nedeni 64 bitlik bir uygulama geliştirmemekte, ancak Visual C++ 64 bit derleyicilerinin birine yüklememiş olmanız olabilir. Bu durumda, 64 bit yapılandırma kullanılabilir olmayacaktır. Bu sorunu onarmak için, Visual Studio için yükleyiciyi çalıştırın ve eksik C++ bileşenlerini yükleme.

Bu hata, **Configuration Manager** **etkin çözüm yapılandırmasını** değiştirirseniz ve sonra ara proje dosyalarını silmeden önce projeyi derlemeyi denerseniz da oluşabilir. Bu hatayı çözmek için **derleme** menüsünden **çözümü yeniden derle** ' yi seçin. Ayrıca **derleme** menüsünden **Çözümü Temizle** ' yi seçip çözümü oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Araçları hataları ve uyarıları](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
