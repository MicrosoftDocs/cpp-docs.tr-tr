---
title: "Genel Özellikler (Linux C++ derleme görevleri dosyası projesi) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3dec6853-43f6-412b-9806-9bfad333a204
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.BuildLogFile
ms.openlocfilehash: 9507ab2ed54d8160afdd8071b0779b51d6802bef
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="makefile-project-properties-linux-c"></a>Derleme görevleri dosyası proje özellikleri (Linux C++)
Bu bir Linux Makefile proje ile kullanılabilen özellikleri kısmi bir listesidir. Birçok MakeFile proje özellikleri özdeş 

## <a name="general"></a>Genel
Özellik | Açıklama | Seçenekler
--- | ---| ---
Çıktı dizini | Çıktı dosyası dizini için göreli bir yol belirtir; ortam değişkenleri içerebilir.
Ara dizini | Ara dosyası dizine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Günlük dosyası oluşturma | Günlük ne zaman oluşturulacağını etkin yazmak için yapılandırma günlük dosyasını belirtir.
Yapılandırma türü | Bu yapılandırma oluşturur çıktı türünü belirtir. | **Dinamik kitaplığı (.so)** -dinamik kitaplığı (.so)<br>**Statik kitaplık (bir)** -statik kitaplık (bir)<br>**Uygulama (.out)** -uygulama (.out)<br>**Derleme görevleri dosyası** -derleme görevleri dosyası<br>
Uzak yapı makinesi | Hedef makine ya da uzak yapı için kullanmak üzere cihaz dağıtmak ve hata ayıklama.
Uzak derleme kök dizini | Uzak makinenin veya cihazın bir dizin yolunu belirtir.
Uzak derleme proje dizini | Uzak makinede veya aygıt proje için bir dizin yolunu belirtir.

## <a name="debugging"></a>Hata Ayıklama
Bkz: [hata ayıklayıcı özellikleri (Linux C++)](debugging-linux.md)

## <a name="copy-sources"></a>Kaynakları kopyalama
Bkz: [kopyalama kaynakları proje özellikleri (Linux C++)](copy-sources-project.md).

## <a name="build-events"></a>Derleme olayları

### <a name="pre-build-event"></a>Derleme öncesi olay
Özellik | Açıklama
--- | ---
Komut satırı | Oluşturma öncesi olay aracını çalıştırmak için komut satırını belirtir.
Açıklama | Görüntülenecek oluşturma öncesi olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzak sisteme kopyalama için ek dosyalar belirtir. İsteğe bağlı olarak listesi yerel bir uzak eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: fullremotepath1; = fulllocalpath2: yerel bir dosya kopyalanabildiği belirtilen uzak konuma uzak sistem üzerindeki fullremotepath2 =.

### <a name="post-build-event"></a>Derleme sonrası olay
Komut satırı | Oluşturma sonrası olay aracını çalıştırmak için komut satırını belirtir.
Açıklama | Görüntülenecek oluşturma sonrası olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzak sisteme kopyalama için ek dosyalar belirtir. İsteğe bağlı olarak listesi yerel bir uzak eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: fullremotepath1; = fulllocalpath2: yerel bir dosya kopyalanabildiği belirtilen uzak konuma uzak sistem üzerindeki fullremotepath2 =.

### <a name="remote-pre-build-event"></a>Uzak oluşturma öncesi olay
Komut satırı | Uzak sistemde çalıştırmak oluşturma öncesi olay aracı için komut satırını belirtir.
Açıklama | Görüntülenecek oluşturma öncesi olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzaktaki sistemden kopyalamak için ek dosyalar belirtir. İsteğe bağlı olarak listeden uzak olarak yerel eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fullremotepath1: fulllocalpath1; = fullremotepath2: Uzak bir dosya kopyalanabildiği yerel makine üzerinde belirtilen konuma fulllocalpath2 =.

### <a name="remote-post-build-event"></a>Uzak oluşturma sonrası olay
Komut satırı | Uzak sistemde çalıştırmak oluşturma sonrası olay aracı için komut satırını belirtir.
Açıklama | Görüntülenecek oluşturma sonrası olay aracı için bir açıklama belirtir.
Yapı kullanımda | Bu yapı olay yapılandırmasına yapıdan tutulup tutulmayacağını belirtir.
Kopyalamak için ek dosyalar | Uzaktaki sistemden kopyalamak için ek dosyalar belirtir. İsteğe bağlı olarak listeden uzak olarak yerel eşleme çiftlerine böyle bir söz dizimi kullanılarak sağlanabilir: fullremotepath1: fulllocalpath1; = fullremotepath2: Uzak bir dosya kopyalanabildiği yerel makine üzerinde belirtilen konuma fulllocalpath2 =.

## <a name="cc"></a>C/C++

### <a name="intellisense"></a>IntelliSense
IntelliSense özellikleri ipuçları için IntelliSense altyapısı sağlamak üzere proje veya dosya düzeyinde ayarlanabilir. Derleme etkilemez.

Özellik | Açıklama
--- | ---
Arama Yolu Ekle | Eklenen dosyalar çözmek için Include arama yolu belirtir.
Zorlanan içerir | Dahil edilen zorlanır dosyalarını belirtir.
Önişlemci tanımları | Ön İşlemci kaynak dosyalar tarafından kullanılan tanımlar belirtir.
Önişlemci tanımları tanımlarını Kaldır | Bir veya daha fazla önişlemci undefines belirtir.     (/U[macro])
Ek Seçenekler | C++ dosyalarını ayrıştırırken IntelliSense tarafından kullanılacak ek derleyici anahtarları belirtir.

### <a name="build"></a>Derleme
Özellik | Açıklama
--- | ---
Komut satırı derleme | 'Derleme' komutunu çalıştırmak için komut satırını belirtir.
Tüm komut satırı yeniden oluşturma | 'Rebuild All' komutunu çalıştırmak için komut satırını belirtir.
Komut satırı Temizle | 'Temiz' komutunu çalıştırmak için komut satırını belirtir.

### <a name="remote-build"></a>Uzak derleme
Özellik | Açıklama
--- | ---
Komut satırı derleme | 'Derleme' komutunu çalıştırmak için komut satırını belirtir. Bu uzak sistemde yürütülür.
Tüm komut satırı yeniden oluşturma | 'Rebuild All' komutunu çalıştırmak için komut satırını belirtir. Bu uzak sistemde yürütülür.
Komut satırı Temizle | 'Temiz' komutunu çalıştırmak için komut satırını belirtir. Bu uzak sistemde yürütülür.
Çıktılar | Uzak sistem üzerindeki uzak yapı tarafından oluşturulan çıkış belirtir.

