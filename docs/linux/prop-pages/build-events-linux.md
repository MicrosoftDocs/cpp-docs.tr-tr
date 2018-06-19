---
title: Uzaktan derleme olaylarını (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 9/26/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 165d3690-5bd8-4b0b-bc66-8b699d85a61b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 38c036bf747115823b853d0d66077f4402a7f7ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338412"
---
# <a name="build-event-properties-linux-c"></a>Yapı olay özellikleri (Linux C++) 

## <a name="pre-build-event"></a>Derleme öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Oluşturma öncesi olay aracını çalıştırmak için komut satırını belirtir.
Açıklama | Görüntülenecek oluşturma öncesi olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzak sisteme kopyalama için ek dosyalar belirtir. İsteğe bağlı olarak listesi yerel bir uzak eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: fullremotepath1; = fulllocalpath2: yerel bir dosya kopyalanabildiği belirtilen uzak konuma uzak sistem üzerindeki fullremotepath2 =.

## <a name="pre-link-event"></a>Bağlama öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Bağlama öncesi olay aracını çalıştırmak için komut satırını belirtir.
Açıklama | Görüntülenecek bağlama öncesi olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzak sisteme kopyalama için ek dosyalar belirtir. İsteğe bağlı olarak listesi yerel bir uzak eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: fullremotepath1; = fulllocalpath2: yerel bir dosya kopyalanabildiği belirtilen uzak konuma uzak sistem üzerindeki fullremotepath2 =.

## <a name="post-build-event"></a>Derleme sonrası olay

Özellik | Açıklama
--- | ---
Komut satırı | Oluşturma sonrası olay aracını çalıştırmak için komut satırını belirtir.
Açıklama | Görüntülenecek oluşturma sonrası olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzak sisteme kopyalama için ek dosyalar belirtir. İsteğe bağlı olarak listesi yerel bir uzak eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: fullremotepath1; = fulllocalpath2: yerel bir dosya kopyalanabildiği belirtilen uzak konuma uzak sistem üzerindeki fullremotepath2 =.

## <a name="remote-pre-build-event"></a>Uzak oluşturma öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Uzak sistemde çalıştırmak oluşturma öncesi olay aracı için komut satırını belirtir.
Açıklama | Görüntülenecek oluşturma öncesi olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzaktaki sistemden kopyalamak için ek dosyalar belirtir. İsteğe bağlı olarak listeden uzak olarak yerel eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fullremotepath1: fulllocalpath1; = fullremotepath2: Uzak bir dosya kopyalanabildiği yerel makine üzerinde belirtilen konuma fulllocalpath2 =.

## <a name="remote-pre-link-event"></a>Uzak bağlama öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Uzak sistemde çalıştırmak bağlama öncesi olay aracı için komut satırını belirtir.
Açıklama | Görüntülenecek bağlama öncesi olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzaktaki sistemden kopyalamak için ek dosyalar belirtir. İsteğe bağlı olarak listeden uzak olarak yerel eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fullremotepath1: fulllocalpath1; = fullremotepath2: Uzak bir dosya kopyalanabildiği yerel makine üzerinde belirtilen konuma fulllocalpath2 =.

## <a name="remote-post-build-event"></a>Uzak oluşturma sonrası olay

Özellik | Açıklama
--- | ---
Komut satırı | Uzak sistemde çalıştırmak oluşturma sonrası olay aracı için komut satırını belirtir.
Açıklama | Görüntülenecek oluşturma sonrası olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzaktaki sistemden kopyalamak için ek dosyalar belirtir. İsteğe bağlı olarak listeden uzak olarak yerel eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fullremotepath1: fulllocalpath1; = fullremotepath2: Uzak bir dosya kopyalanabildiği yerel makine üzerinde belirtilen konuma fulllocalpath2 =.
