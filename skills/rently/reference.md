# Rently CLI — Full Command Reference

## auth — Manage authentication
| Command | Description |
|---------|-------------|
| `rently auth login --tenant <name> --client-id <id> --client-secret <secret>` | Authenticate |
| `rently auth status` | Show current auth status |
| `rently auth logout` | Remove credentials |

## search — Search availability and pricing
| Command | Description |
|---------|-------------|
| `rently search availability --from <datetime> --to <datetime> --from-place <id>` | Search available cars |
| `rently search price --from <datetime> --to <datetime> --from-place <id> --model-id <id>` | Get booking price |
| `rently search additionals-price --from-date <datetime> --to-date <datetime>` | Get additional services pricing |

## bookings — Manage bookings
| Command | Description |
|---------|-------------|
| `rently bookings list [--status <status>] [--offset <n>] [--limit <n>]` | List bookings |
| `rently bookings create [--json-body <json>]` | Create booking |
| `rently bookings update [--json-body <json>]` | Update booking |
| `rently bookings cancel [--booking-id <id> --lastname <name>]` | Cancel booking |
| `rently bookings cancel-external [--external-booking-id <id>]` | Cancel by external ID |
| `rently bookings reserve [--booking-id <id> --lastname <name>]` | Reserve booking |
| `rently bookings get <booking-id>` | Get booking details |
| `rently bookings get-with-promotion <booking-id> --promotion-id <id>` | Get with promotion |
| `rently bookings apply-promotion <booking-id> --promotion-id <id>` | Apply promotion |
| `rently bookings get-external <booking-id>` | Get by external ID |
| `rently bookings attach-files [--json-body <json>]` | Attach files |
| `rently bookings attach-invoice-files [--json-body <json>]` | Attach invoice files |
| `rently bookings get-attachments <booking-id>` | Get attachments |
| `rently bookings add-comment [--message <text> --comment-type <type> --important]` | Add comment |
| `rently bookings add-driver <booking-id> <customer-id>` | Add driver |
| `rently bookings get-drivers <booking-id>` | Get drivers |
| `rently bookings get-links <booking-id>` | Get links |
| `rently bookings get-cancellation <booking-id>` | Get cancellation info |

## payments — Manage booking payments
| Command | Description |
|---------|-------------|
| `rently payments pay [--booking-id <id> --amount <n> --gateway-id <gw> --currency-code <c>]` | Process payment |
| `rently payments get <booking-id>` | Get payments for booking |
| `rently payments cancel --payment-id <id>` | Cancel payment |

## customers — Manage customers
| Command | Description |
|---------|-------------|
| `rently customers list [--filter <text>] [--offset <n>] [--limit <n>]` | Search/list customers |
| `rently customers get <customer-id>` | Get customer details |
| `rently customers create [--firstname <n> --lastname <n> --document-id <d> --email-address <e>]` | Create customer |
| `rently customers update [--json-body <json>]` | Update customer |
| `rently customers create-or-update [--json-body <json>]` | Create or update |
| `rently customers get-bookings <customer-id> [--offset <n>] [--limit <n>]` | Get bookings |
| `rently customers get-booking <customer-id> <booking-id>` | Get specific booking |
| `rently customers get-payment-method <customer-id> --gateway-id <id>` | Get payment method |
| `rently customers set-payment-method <customer-id> [--json-body <json>]` | Set payment method |
| `rently customers add-comment <customer-id> [--message <text> --comment-type <type> --important]` | Add comment |
| `rently customers get-attachments <customer-id>` | Get attachments |
| `rently customers attach-files <customer-id> --json-body <json>` | Attach files (array body) |
| `rently customers upload-document-images <customer-id>` | Upload document images |

## cars — Manage fleet cars
| Command | Description |
|---------|-------------|
| `rently cars list [--active <bool>] [--offset <n>] [--limit <n>]` | List cars |
| `rently cars get <id>` | Get car details |
| `rently cars get-bookings <id> [--offset <n>] [--limit <n>]` | Get car bookings |
| `rently cars relocate [--car-id <id> --place-id <id> --km <n> --gasoline <n>]` | Relocate car |
| `rently cars transfer [--car-id <id> --place-id <id> --from-date <dt> --to-date <dt>]` | Transfer car |
| `rently cars list-files <car-id>` | List car files |
| `rently cars attach-files <car-id> --json-body <json>` | Attach files (array body) |

## operations — Manage deliveries and returns
| Command | Description |
|---------|-------------|
| `rently operations list-deliveries --branch-office-id <id> [--date <datetime>]` | List deliveries |
| `rently operations list-returns --branch-office-id <id> [--date <datetime>]` | List returns |
| `rently operations deliver [--booking-id <id> --kilometers <n> --gasoline <n> --make-delivery --run-validations]` | Deliver car |
| `rently operations return [--booking-id <id> --kilometers <n> --gasoline <n> --make-return --run-validations --date <dt>]` | Return car |

## incidents — Manage incidents
| Command | Description |
|---------|-------------|
| `rently incidents types` | Get incident types |
| `rently incidents get <incident-id>` | Get incident |
| `rently incidents create [--incident-date <dt> --car-id <id> --incident-type-id <n> --booking-id <n> --notes <text> --has-recovery]` | Create incident |
| `rently incidents attach-files <incident-id>` | Attach files |

## infractions — Manage infractions
| Command | Description |
|---------|-------------|
| `rently infractions list <customer-id> [--offset <n>] [--limit <n>]` | List customer infractions |
| `rently infractions get <customer-id> <infraction-id>` | Get infraction |
| `rently infractions create [--plate <p> --date <dt> --amount <n> --jurisdiction <j> --infraction-type <t>]` | Create infraction |
| `rently infractions add-to-booking --json-body <json>` | Add to booking (array body) |
| `rently infractions pay [--infraction-id <id> --amount <n> --gateway-id <gw> --currency-code <c>]` | Pay infraction |
| `rently infractions attach-files [--json-body <json>]` | Attach files |
| `rently infractions settings` | Get collector settings |
| `rently infractions charge <infraction-id>` | Try to charge |

## notifications — Manage email notifications
| Command | Description |
|---------|-------------|
| `rently notifications list` | List templates |
| `rently notifications send [--mail-notification-id <n> --entity-id <id> --to <email> --selected-language <lang>]` | Send notification |
| `rently notifications send-known <guid> [--json-body <json>]` | Send known template |

## services — Manage vehicle services
| Command | Description |
|---------|-------------|
| `rently services get <id>` | Get service details |
| `rently services types` | Get service types |
| `rently services create [--car-id <id> --service-type-id <n> --from-date <dt> --to-date <dt> --notes <text>]` | Create service |
| `rently services update [--id <n> --car-id <id> --service-type-id <n> --status <n>]` | Update service |

## storage — Manage web file storage
| Command | Description |
|---------|-------------|
| `rently storage list` | List web files |
| `rently storage add [--file-name <name> --base64-file <base64>]` | Add web file |

## tolls — Manage toll charges
| Command | Description |
|---------|-------------|
| `rently tolls find-by-plates --model <json-array>` | Find bookings by plates |
| `rently tolls find-by-transponders --find-by-transponders <json-array>` | Find by transponders |
| `rently tolls add --json-body <json>` | Add toll charges (array body) |

## agreements — Manage commercial agreements
| Command | Description |
|---------|-------------|
| `rently agreements list [--agency-id <id>] [--agency-iata <code>]` | List agreements |
| `rently agreements list-all` | List all agreements |
| `rently agreements get <code>` | Get agreement by code |

## configurations — View system configurations
| Command | Description |
|---------|-------------|
| `rently configurations attachments` | Attachment type configs |
| `rently configurations tax-payer-types` | Tax payer types |
| `rently configurations bookings` | Booking configs |
| `rently configurations mails` | Mail configs |
| `rently configurations document-types` | Document types |
| `rently configurations gateway-credentials` | Payment gateway credentials |
| `rently configurations payment-accounts` | Payment accounts |
| `rently configurations general-settings` | General tenant settings |

## info — General reference data
| Command | Description |
|---------|-------------|
| `rently info places` | Get places |
| `rently info place-types` | Get place types |
| `rently info branch-offices` | Get branch offices |
| `rently info categories` | Get vehicle categories |
| `rently info additionals` | Get additional services |
| `rently info additionals-with-stock --category-id <id> --model-id <id> --from <dt> --to <dt> --price <n>` | Additionals with stock |
| `rently info promotions` | Get active promotions |
| `rently info validate-promotion <code> [--from-date <dt>] [--to-date <dt>]` | Validate promotion |
| `rently info currencies` | Get currencies |
| `rently info languages` | Get language codes |
| `rently info languages-info` | Get detailed language info |
| `rently info holidays [--branchofficeid <id>]` | Get holidays |
| `rently info attention-schedule` | Get attention schedule |

## checkin — Self check-in
| Command | Description |
|---------|-------------|
| `rently checkin update [--json-body <json>]` | Update self check-in |

## inout — In & Out app operations
| Command | Description |
|---------|-------------|
| `rently inout feature-flags` | Get feature flags |
| `rently inout branch-offices` | Get branch offices |
| `rently inout bookings --branch-office-id <id> [--date <dt>]` | Get bookings for branch |
| `rently inout update-dropoff <booking-id> [--place-id <id>]` | Update dropoff place |
| `rently inout branch-office-places <branch-office-id>` | Get places for branch |
| `rently inout search --branch-office-id <id> --filter <text>` | Search bookings |
| `rently inout booking-detail <booking-id>` | Get booking detail |
| `rently inout cancel-booking <booking-id>` | Cancel booking |
| `rently inout available-cars <booking-id>` | Available cars for booking |
| `rently inout assign-car <booking-id> <car-id>` | Assign car |
| `rently inout get-protocol <booking-id>` | Get protocol |
| `rently inout save-protocol [--booking-id <n> --car-id <id> --kilometers <n> --gasoline <n> --type <t>]` | Save protocol |
| `rently inout download-pdf --booking-id <id> [--is-delivery]` | Download PDF |
| `rently inout attach-files [--json-body <json>]` | Attach files |
| `rently inout attach-files-binary [--booking-id <id>] [--car-id <id>]` | Attach binary files |
| `rently inout get-customer <id>` | Get customer |
| `rently inout update-customer [--json-body <json>]` | Update customer |
| `rently inout get-delivery <booking-id>` | Get delivery response |
| `rently inout get-return <booking-id>` | Get return response |
| `rently inout available-cars-branch <branch-office-id>` | Cars at branch |
| `rently inout cars-protocols` | Get cars protocols |
| `rently inout save-cars-protocol [--json-body <json>]` | Save cars protocol |
| `rently inout get-protocol-by-id <id>` | Get protocol by ID |
| `rently inout incident-types` | Get incident types |

## odata — Advanced queries with OData filters

All OData subcommands support: `--filter`, `--select`, `--orderby`, `--top`, `--skip`, `--expand`, `--id`

| Command | Description |
|---------|-------------|
| `rently odata bookings [--customer-id <id>]` | Query bookings |
| `rently odata customers` | Query customers |
| `rently odata agencies [--search <text>]` | Query agencies |
| `rently odata categories` | Query vehicle categories |
| `rently odata models` | Query vehicle models |
| `rently odata places` | Query places |
| `rently odata brands` | Query booking brands |

## profile — View account profile
| Command | Description |
|---------|-------------|
| `rently profile get` | Get authenticated user profile |

## JSON Body Schemas

### bookings create / update
```json
{
  "Id": 0, "Customer": { "Id": 123 }, "Category": { "Id": 1 },
  "FromDate": "2026-04-01T10:00:00", "ToDate": "2026-04-05T10:00:00",
  "DeliveryPlace": { "Id": 9 }, "ReturnPlace": { "Id": 9 },
  "Currency": "USD", "IlimitedKm": true,
  "Additionals": [{ "Additional": { "Id": 40 }, "Quantity": 1 }]
}
```

### bookings attach-files / attach-invoice-files
```json
{ "BookingId": "123", "Files": [{ "Name": "doc.pdf", "Content": "<base64>", "Type": "application/pdf" }] }
```

### payments pay
```json
{
  "BookingId": 123, "Amount": 199.99, "CurrencyCode": "USD",
  "GatewayId": "STRIPE", "TransactionId": "TXN123",
  "BillingInformation": { "FirstName": "John", "LastName": "Doe", "DocumentId": "123456789", "EmailAddress": "john@example.com" }
}
```

### customers create / update / create-or-update
```json
{
  "Id": 0, "Firstname": "John", "Lastname": "Doe",
  "DocumentId": "123456789", "DocumentTypeId": 1,
  "EmailAddress": "john@example.com", "CellPhone": "+1555012345",
  "Address": "123 Main St", "Country": "US", "BirthDate": "1990-01-01T00:00:00"
}
```

### customers set-payment-method
```json
{
  "GatewayId": "STRIPE", "RentlyCustomerId": 123,
  "GatewayCustomerId": "cus_123", "GatewayPaymentMethodId": "pm_123",
  "CreditCard": { "Type": "VISA", "Number": "4242...", "ExpirationMonth": 12, "ExpirationYear": 2027, "CardHolderName": "John Doe" }
}
```

### infractions add-to-booking (array body)
```json
[{ "ReqId": 1, "BookingId": 123, "Date": "2026-04-01T10:00:00", "Act": "SPEED_VIOLATION", "InfractionAmount": 150, "FeeAmount": 25, "Jurisdiction": "New York", "InfractionType": "SpeedingTicket" }]
```

### tolls add (array body)
```json
[{ "ReqId": 1, "BookingId": 2300, "PlateNumber": "ABC123", "Date": "2026-04-01T10:00:00", "TollAmount": 15.50 }]
```

### checkin update
```json
{ "Id": 2300, "Customer": { "Id": 123, "Firstname": "John", "Lastname": "Doe", "DocumentId": "123456789", "DocumentTypeId": 1, "EmailAddress": "john@example.com" }, "Extra": "", "Additionals": [] }
```

### inout save-protocol
```json
{ "AppProtocolId": 1, "BookingId": 2300, "CarId": "ABC123", "Kilometers": 15000, "Gasoline": 8, "Notes": "", "Type": "Delivery", "ResponseData": [] }
```

## Exit Codes
| Code | Meaning |
|------|---------|
| 0 | Success |
| 1 | Business error |
| 2 | Authentication error (401/403) |
| 3 | Network error / timeout |
| 4 | CLI usage error |
