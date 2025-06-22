# n8n Google Routes Optimization Workflow

[![Demo Video](https://img.shields.io/badge/Demo-YouTube-red)](https://www.youtube.com/watch?v=EG-A2JjyxDg)
[![n8n](https://img.shields.io/badge/n8n-Compatible-blue)](https://n8n.io)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A powerful n8n workflow that provides intelligent route optimization for service businesses using Google Maps APIs. This workflow helps lawn care, HVAC, plumbing, cleaning, pest control, and other field service companies optimize their daily routes, reduce fuel costs, and increase operational efficiency.

## 🎯 Why Use This Workflow?

**Proven ROI for Service Businesses:**
- **15% fuel cost reduction** through optimized routing
- **20% improvement in operational efficiency** 
- **80% reduction in daily planning time** (from manual to automated)
- **2-3 additional jobs per vehicle per month** through better scheduling
- **Typical payback period: 8-12 months** for most service businesses

### Real-World Impact
Based on extensive research and industry case studies, businesses implementing route optimization typically see:
- Monthly fuel savings of $90-200 per vehicle
- Time savings worth $400-800 monthly in labor costs
- Additional revenue of $150-300 per vehicle from extra job capacity
- **Total monthly benefit: $640-1,300 per vehicle**

## 🚀 Features

- **Intelligent Route Optimization**: Automatically calculates the most efficient routes using Google Maps
- **Multi-Stop Planning**: Handles complex routes with multiple customer locations
- **Real-Time Traffic Integration**: Considers current traffic conditions for optimal routing
- **Flexible Input Methods**: Accept addresses, coordinates, or customer data from various sources
- **Telegram Bot Integration**: Easy-to-use interface for field teams and dispatchers
- **Automated Scheduling**: Reduces manual planning time by 80%
- **Cost Analysis**: Built-in calculations for fuel savings and efficiency gains

## 📋 Prerequisites

Before installing this workflow, ensure you have:

1. **n8n Instance**: A running n8n installation (cloud or self-hosted)
2. **Google Cloud Account**: For accessing Google Maps APIs
3. **Google Maps API Keys**: With the following APIs enabled:
   - Google Maps Directions API
   - Google Maps Geocoding API
   - Google Maps Distance Matrix API
4. **Telegram Bot** (optional): For team interface functionality

## 🛠️ Installation

### Step 1: Download the Workflow

1. Download the workflow JSON file from this repository
2. Copy the workflow content to your clipboard

### Step 2: Import to n8n

1. Open your n8n instance
2. Click **"+"** to create a new workflow
3. Click **"Import from clipboard"** 
4. Paste the workflow JSON content
5. Click **"Import"**

### Step 3: Configure API Credentials

1. **Google Maps API Setup**:
   - Go to [Google Cloud Console](https://console.cloud.google.com/)
   - Create a new project or select existing one
   - Enable Google Maps APIs (Directions, Geocoding, Distance Matrix)
   - Create API key and restrict it to your APIs
   - Copy the API key

2. **Add Credentials in n8n**:
   - Go to **Settings > Credentials**
   - Create new **HTTP Request** credential for Google APIs
   - Add your Google Maps API key

3. **Configure Workflow Nodes**:
   - Open each Google Maps API node in the workflow
   - Select your credential
   - Test the connection

### Step 4: Set Up Telegram Bot (Optional)

1. Create a bot with [@BotFather](https://t.me/botfather) on Telegram
2. Get your bot token
3. Add Telegram credentials in n8n
4. Configure the Telegram nodes in the workflow

## 💡 How to Use

### Basic Route Optimization

1. **Prepare Your Data**: Create a list of customer addresses or coordinates
2. **Trigger the Workflow**: Send data via:
   - Manual execution with test data
   - Webhook trigger from your CRM/booking system
   - Telegram bot commands
   - Scheduled automation

3. **Input Format Example**:
```json
{
  "jobs": [
    {
      "customer": "John Smith",
      "address": "123 Main St, Anytown, ST 12345",
      "serviceType": "lawn_mowing",
      "estimatedDuration": 30
    },
    {
      "customer": "Jane Doe", 
      "address": "456 Oak Ave, Anytown, ST 12345",
      "serviceType": "fertilization",
      "estimatedDuration": 45
    }
  ],
  "startLocation": "Your Business Address",
  "vehicleCount": 2
}
```

4. **Get Optimized Routes**: The workflow returns:
   - Optimized route order
   - Turn-by-turn directions
   - Estimated travel times
   - Fuel cost calculations
   - Efficiency metrics

### Advanced Usage

**Integration with Business Systems**:
- Connect to your CRM for automatic daily route planning
- Integrate with booking systems for real-time optimization
- Set up scheduled runs for next-day route preparation
- Use webhooks to trigger optimization when new jobs are added

**Telegram Bot Commands** (if configured):
- `/optimize` - Optimize today's routes
- `/routes [date]` - Get routes for specific date
- `/add [address]` - Add new job to route
- `/status` - Check optimization status

## 🎬 Demo Video

Watch our comprehensive demo showing the workflow in action:

[![Demo Video](https://img.youtube.com/vi/EG-A2JjyxDg/maxresdefault.jpg)](https://www.youtube.com/watch?v=EG-A2JjyxDg)

The demo covers:
- Installing and configuring the workflow
- Setting up Google Maps API integration
- Running route optimization with real addresses
- Interpreting results and savings calculations
- Telegram bot integration example

## 🏢 Business Impact

### Service Industries That Benefit:

- **Lawn Care & Landscaping**: Optimize mowing routes, reduce fuel costs
- **HVAC Services**: Efficient technician routing, faster response times  
- **Plumbing Services**: Emergency and scheduled call optimization
- **Cleaning Services**: Multi-location route planning
- **Pest Control**: Territory-based route optimization
- **Home Services**: Any business with mobile service teams

### Typical Savings for a 3-Vehicle Operation:

| Metric | Before Optimization | After Optimization | Monthly Savings |
|--------|-------------------|-------------------|----------------|
| Fuel Costs | $1,800 | $1,530 | $270 |
| Labor Hours | 480 hours | 384 hours | $2,400 |
| Planning Time | 22 hours | 4 hours | $450 |
| Additional Jobs | 0 | 7.5 jobs | $565 |
| **Total Monthly Benefit** | | | **$3,685** |

## ⚙️ Configuration Options

### Workflow Variables
- `MAX_STOPS_PER_ROUTE`: Maximum stops per vehicle (default: 15)
- `BREAK_DURATION`: Lunch break time in minutes (default: 30)
- `WORK_START_TIME`: Daily start time (default: "08:00")
- `WORK_END_TIME`: Daily end time (default: "17:00")
- `FUEL_COST_PER_MILE`: Current fuel cost calculation (default: $0.56)

### Optimization Parameters
- Travel time vs distance priority
- Vehicle capacity constraints
- Service time windows
- Customer priority levels
- Geographic clustering preferences

## 🔧 Customization

The workflow is designed to be flexible and can be customized for your specific business needs:

1. **Modify Input Sources**: Connect to your existing CRM or booking system
2. **Adjust Optimization Logic**: Change routing priorities and constraints  
3. **Customize Output Format**: Modify the results to match your team's needs
4. **Add Business Rules**: Include customer preferences, technician skills, etc.
5. **Integrate Notifications**: Add SMS, email, or app notifications

## 📊 ROI Calculator

Use our [Route Optimization ROI Calculator](https://github.com/imagicrafter/n8n-google-routes-workflow/blob/main/Route_Optimization_Calc.html) to estimate your potential savings:

- Input your current vehicle count and operation details
- See projected fuel, time, and planning savings
- Calculate payback period for implementation
- Compare costs with benefits over 1-3 years

## 🤝 Support & Community

- **Issues**: Report bugs or request features via GitHub Issues
- **Documentation**: Full setup guides and troubleshooting tips
- **Community**: Join our discussions for tips and best practices
- **Custom Development**: Contact us for enterprise customizations

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📞 About

Developed by [ImagiCrafter AI](https://imagicrafterai.com) as part of our commitment to helping small businesses leverage automation and AI for operational efficiency.

**Business Impact Research Sources**: Our ROI calculations are based on extensive research including academic studies from Transportation Research journals, industry analysis from McKinsey & Company, and real-world case studies from service businesses across lawn care, HVAC, plumbing, and other field service industries.

---

### Quick Start Checklist

- [ ] n8n instance running
- [ ] Google Maps API key obtained
- [ ] APIs enabled (Directions, Geocoding, Distance Matrix)
- [ ] Workflow imported to n8n
- [ ] Credentials configured
- [ ] Test run completed successfully
- [ ] Telegram bot configured (optional)
- [ ] Business data integration planned

**Ready to optimize your routes and boost your bottom line? Get started today!**# n8n-google-routes-workflow
