---
title: RESULT_CODE numaralandırması
description: C++ Build Insights SDK 'Sı RESULT_CODE enum başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RESULT_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3d9d18d535d15d04a2e449bdbbf693364276a518
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922412"
---
# <a name="result_code-enum"></a>RESULT_CODE numaralandırması

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`RESULT_CODE`Enum, başarı ve başarısızlık koşullarını açıklar.

## <a name="members"></a>Üyeler

| Ad | Değer | Açıklama |
|--|--|--|
| `RESULT_CODE_SUCCESS` | 0 (0x00000000) | İşlem başarılı oldu. |
| `RESULT_CODE_FAILURE_ANALYSIS_ERROR` | 1 (0x00000001) | [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md) içindeki geri çağırma işlevlerinizin biri değeri döndürdü `CALLBACK_CODE_ANALYSIS_FAILURE` . Bu değer [CALLBACK_CODE](callback-code-enum.md) numaralandırmasının bir üyesidir. |
| `RESULT_CODE_FAILURE_CANCELLED` | 2 (0x00000002) | [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) veya [RELOG_DESCRIPTOR](relog-descriptor-struct.md) içindeki geri çağırma işlevlerinizin biri değeri döndürdü `CALLBACK_CODE_ANALYSIS_CANCEL` . Bu değer [CALLBACK_CODE](callback-code-enum.md) numaralandırmasının bir üyesidir. |
| `RESULT_CODE_FAILURE_INVALID_INPUT_LOG_FILE` | 3 (0x00000003) | Belirtilen Windows için giriş olayı Izleme (ETW) izlemesi geçersiz. |
| `RESULT_CODE_FAILURE_INVALID_OUTPUT_LOG_FILE` | 4 (0x00000004) | Belirtilen çıkış ETW izlemesi geçersiz. |
| `RESULT_CODE_FAILURE_MISSING_ANALYSIS_CALLBACK` | 5 (0x00000005) | [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) yapısı doğru bir şekilde başlatılmadı. |
| `RESULT_CODE_FAILURE_MISSING_RELOG_CALLBACK` | 6 (0x00000006) | [RELOG_CALLBACKS](relog-callbacks-struct.md) yapısı doğru bir şekilde başlatılmadı. |
| `RESULT_CODE_FAILURE_OPEN_INPUT_TRACE` | 7 (0x00000007) | Giriş ETW izlemesi açılamadı. |
| `RESULT_CODE_FAILURE_PROCESS_TRACE` | 8 (0x00000008) | Giriş ETW izlemesi işlenirken bir hata oluştu. |
| `RESULT_CODE_FAILURE_START_RELOGGER` | 9 (0x00000009) | Yeniden günlüğe kaydetme oturumu başlatılmaya çalışılırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_DROPPED_EVENTS` | 10 (0x0000000A) | Giriş ETW izlemesinin önemli olayları eksik. |
| `RESULT_CODE_FAILURE_UNSUPPORTED_OS` | 11 (0x0000000B) | C++ derleme öngörülerini desteklenmeyen bir Windows sürümünde kullanıyorsunuz. |
| `RESULT_CODE_FAILURE_INVALID_TRACING_SESSION_NAME` | 12 (0x0000000C) | Belirtilen oturum adı geçersiz. |
| `RESULT_CODE_FAILURE_INSUFFICIENT_PRIVILEGES` | 13 (0x0000000D) | Bu işlem yönetici ayrıcalıkları gerektirir. |
| `RESULT_CODE_FAILURE_GENERATE_GUID` | 14 (0x0000000E) | GUID üretilirken bir hata oluştu. |
| `RESULT_CODE_FAILURE_OBTAINING_TEMP_DIRECTORY` | 15 (0x0000000F) | Geçici dizin yolu tespit edilmeye çalışılırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_CREATE_TEMPORARY_DIRECTORY` | 16 (0x00000010) | İzleme oturumunun başlatılması için geçici bir dizin oluşturulmaya çalışılırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_START_SYSTEM_TRACE` | 17 (0x00000011) | Sistem izlemesi başlatılmaya çalışılırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_START_MSVC_TRACE` | 18 (0x00000012) | MSVC izlemesi başlatılmaya çalışılırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_STOP_MSVC_TRACE` | 19 (0x00000013) | MSVC izlemesi durdurulmaya çalışılırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_STOP_SYSTEM_TRACE` | 20 (0x00000014) | Sistem izlemesi başlatılmaya çalışılırken bir hata oluştu. |
| `RESULT_CODE_FAILURE_SESSION_DIRECTORY_RESOLUTION` | 21 (0x00000015) | Bir izleme durduruldu, ancak izleme oturumunun geçici dizini bulunamıyor. |
| `RESULT_CODE_FAILURE_MSVC_TRACE_FILE_NOT_FOUND` | 22 (0x00000016) | Durdurulan MSVC izlemesinin izleme dosyası bulunamıyor. |
| `RESULT_CODE_FAILURE_MERGE_TRACES` | 23 (0x00000017) | Izleme, çekirdek Izleme denetimi kullanılarak birleştirilirken bir hata oluştu. |
| `RESULT_CODE_FAILURE_UNKNOWN_ERROR` | 24 (0x00000018) | Bilinmeyen bir hata oluştu. |

::: moniker-end
